# Jenkins 와 Gitlab 통합

이 문서는 DevOps의 한 방법으로 깃랩을 SCM(Source Control Management) 시스템으로만 사용하고, 젠킨스를 CI/CD로 사용하는 방법에 대해 테스트한 후 발생한 문제점과 해결책들을 정리해봤습니다.

# 1. 설치 방법

1. 설치 방법에서는 PC, 맥, AWS EC2 등에서 사용할 수 있습니다. 

# 2. 맥에서 설치 방법

주로 맥을 사용하기 많이 사용하기 때문에 맥 로컬 호스트로 설치하는 방법을 먼저 설명하자면 다음과 같습니다.

1) [Gitlab 웹사이트](https://gitlab.com)로 접속해서 무료로 사용할 수 있는 Community Edition Service 으로 접속하여 회원 가입해 로그인하기 바랍니다. 
2) [Install Jenkins on Mac](https://www.knowledgehut.com/blog/devops/install-jenkins-on-mac) 문서를 보고 따라 도커까지 설치했습니다.
3) 최근 맥에서 M1칩 (ARM) 용 맥북이 많이 나와서 Homebrew로 설치 방법은 [M1칩 Mac에서 Homebrew 설치 방법](https://designdepot.tistory.com/209) 문서를 참고하시기 바랍니다.

#### 3-1) Mac에서 Homebrew 설치 후 zsh: command not found: brew 에러 메시지가 나오면 다음과 같이 조치하기 바랍니다. 
#### 3-2) 맥 터미널에서 eval $(/opt/homebrew/bin/brew shellenv) 명령어를 수행하시면 정상적으로 brew 명령어를 사용할 수 있습니다. 
#### 3-3) 터미널을 켤 때 마다 Homebrew 를 자동으로 실행하려면, 맥 터미널에서 vi ~/.zshrc 파일을 편집해서 맨 마지막 줄에 eval $(/opt/homebrew/bin/brew shellenv) 명령문을 추가시켜 주면 됩니다.
#### 3-4) 만일 M1칩 맥이 아니라면, 환경변수를 export PATH=/usr/local/bin:/usr/local/sbin:$PATH 추가시켜 주시기 바랍니다. 

# 3. 로컬 호스트에서 젠킨스와 깃랩 통합하기

1) 깃랩을 SCM 시스템으로만 사용하고 젠킨스를 CI/CD로 사용하는 방법은 [How to integrate Gitlab with Jenkins](https://www.youtube.com/watch?v=-O4tiLzYJMI) 유투브 동영상이 상세히 단계별로 설명이 잘 되어 있어서 이를 참조하였습니다.
2) 위의 동영상대로 일단 진행했습니다만 젠킨스 구버전 방식이라 몇 가지 빌드 애러가 발생해서 다음과 같이 해결하였습니다. 

에러: stderr: No ECDSA host key is known for gitlab.com and you have requested strict checking.
Host key verification failed. fatal: Could not read from remote repository.
해결책: [Jenkins - Resolve No ECDSA Host Key Issue](https://blog.programster.org/jenkins-resolve-no-ecdsa-host-key-issue)
위의 문장대로 따라해 주시기 바랍니다. 

그리고 나서, 다음의 해결책을 실행해 주시기 바랍니다. 

해결책: git ls-remote -h git@gitlab.com:synabreu/tensorflow2.git HEAD 
맥 터미널에서 위의 해결책 명령 문장을 실행시켜주면  YES 로 하면 .ssh/unknown_hosts 파일에 문장이 추가됩니다.
그러면 gitlab 호스트를 로컬에서 인식할 것 입니다.  

에러: Cloning git repo causes error - Host key verification failed. fatal: The remote end hung up unexpectedly.
해결책: ssh-keyscan -t rsa gitlab.com >> ~/.ssh/known_hosts

해결책 명령어를 통해 known hosts 리스트에 깃랩을 추가시킵니다. 

에러: jenkins Couldn't find any revision to build. Verify the repository and branch configuration for this job.
해결책: 젠킨스에서 만드신 Project 의 Configure 에서 [소스 코드 관리] 섹션에서 Git 옵션의 고급(Advanced) 버튼을 누른 후, Branches to build 부분의 Branch Specifier (blank for 'any') 에서 */master 로 되어 있으면 "*/main"으로 변경하면 됩니다. 브랜치명이 젠킨스 설정과 실제 깃랩 SCM이 발생한 에러 입니다.  

* 공통 사항: 해결책을 모두 처리한 다음, 반드시 Jenkins 도커를 다시 재실행시킵니다. 그렇지 않으면 이전의 구성 내용을 저장합니다. 

### 4. 참고 사항

설치 명령어는 다음과 같습니다.

* 젠킨스 최신 LTS 버전 설치: brew install jenkins-lts
* 젠킨스 특정 LTS 버전 지정 설치: brew install jenkins-lts@YOUR_VERSION
* 젠킨스 서비스 시작: brew services start jenkins-lts
* 젠킨스 서비스 재시작: brew services restart jenkins-lts
* Update the Jenkins version: brew upgrade jenkins-lts

### 5. 참고 문서

1. [Jenkins integration](https://docs.gitlab.com/ee/integration/jenkins.html)
2. [Docker Tutorial: A Step by Step Tutorial for Beginners](https://www.simplilearn.com/tutorials/docker-tutorial)
3. [Best Guide on Getting Started with Docker[2023]](https://www.simplilearn.com/tutorials/docker-tutorial/getting-started-with-docker)

 



