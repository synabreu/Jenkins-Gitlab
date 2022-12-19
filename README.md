# Jenkins 와 Gitlab 통합

이 문서는 DevOps의 한 방법으로 깃랩을 SCM(Source Control Management) 시스템으로만 사용하고, 젠킨스를 CI/CD로 사용하는 방법에 대해 테스트한 후 발생한 문제점과 해결책들을 정리해봤습니다.

# 1. 설치 방법

1. 설치 방법에서는 PC, 맥, AWS EC2 등에서 다음과 같이 사용할 수 있습니다.

1) [PC에서 설치 방법](PC_Jenkins.md)
2) [Mac에서 설치 방법](MAC_Jenkins.md)
3) [AWS EC2에서 설치 방법](EC2_Jenkins.md)


# 2. 젠킨스 설치 및 리버스 프록시 설정

1) [젠킨스 설치 및 리버스 프록시 설정](https://kscory.com/dev/jenkins/install)
2) [젠킨스 리버스 프록시 설정 방법 - EC2, https](https://velog.io/@kimsehwan96/Jenkins-%EB%A6%AC%EB%B2%84%EC%8A%A4-%ED%94%84%EB%A1%9D%EC%8B%9C-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95-with-EC2-https)
3) 

# 4. 젠킨스 빌드 및 배포

1) [EC에서 젠킨스로 빌드 - 배포하기](https://velog.io/@junho5336/jenkins%EB%A1%9C-%EB%B9%8C%EB%93%9C-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0#:~:text=jenkins%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EC%83%9D%EC%84%B1,-%EC%83%88%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EB%A5%BC&text=GitHub%20project%EB%A5%BC%20%EB%88%8C%EB%9F%AC%EC%A3%BC%EA%B3%A0,%EB%8C%80%ED%95%9C%20%EC%84%A4%EC%A0%95%EC%9D%84%20%EC%A0%81%EC%96%B4%EC%A4%80%EB%8B%A4.)
2) [젠킨스를 활용한 도커와 스프링부트 CI/CD 구축](https://velog.io/@haeny01/AWS-Jenkins%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-Docker-x-SpringBoot-CICD-%EA%B5%AC%EC%B6%95)
3) [젠킨스와 AWS ECS로 CD 구축](https://ongamedev.tistory.com/475)
4) [[Hands On] CI/CD – Jenkins pipeline을 이용한 ECS 배포](https://tech.cloud.nongshim.co.kr/2021/08/30/hands-on-ci-cd-jenkins-pipeline%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-ecs-%EB%B0%B0%ED%8F%AC/)
5) [젠킨스-AWS ECS-스프링부트 배포 구성](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=cutesboy3&logNo=221643742358)
6) [Setting up a CI/CD pipeline by integrating Jenkins with AWS CodeBuild and AWS CodeDeploy](https://aws.amazon.com/ko/blogs/devops/setting-up-a-ci-cd-pipeline-by-integrating-jenkins-with-aws-codebuild-and-aws-codedeploy/)
7) [젠킨스와 깃랩 연동 및 CI/CD 구축하기](https://pangtrue.tistory.com/356)



# 3. 젠킨스 파이프라인 문법

1) [젠킨스 파이프라인 작성방법 - 기초](https://parkhyeokjin.github.io/devops/2019/10/14/JekinsWritePipeline.html)
2) [젠킨스 파이프라인 문법](https://waspro.tistory.com/554)
3) [Jenkins Tutorial](https://itnext.io/jenkins-tutorial-part-1-pipelines-bd1397cf5509)
4) [Building with Docker Using Jenkins Pipelines](https://www.liatrio.com/blog/building-with-docker-using-jenkins-pipelines)
5) [Jenkins pipeline 이용하기](https://jayy-h.tistory.com/31)


# 4. 젠킨스 파이프라인 구축

1) [Jenkins Pipeline CI/CD 구현 - Github](https://xlffm3.github.io/devops/jenkins-pipeline/)
2) [Jenkins Build를 Gitlab에 Push와 함께 수행하도록 하기](https://tech.osci.kr/2020/01/16/jenkins-build%EB%A5%BC-gitlab%EC%97%90-push%EC%99%80-%ED%95%A8%EA%BB%98-%EC%88%98%ED%96%89%EB%90%98%EB%8F%84%EB%A1%9D-%ED%95%98%EA%B8%B0-2/)
3) [CI/CD - Gitlab 과 Jenkins Maven 빌드 설정](https://zunoxi.tistory.com/102)
4) [CI/CD - Gitlab Webhook으로 Jenkins Build Trigger](https://zunoxi.tistory.com/106?category=950188)
5) [CI/CD - 젠킨스 자동빌드/자동배포(SSH 원격 접속](https://zunoxi.tistory.com/107)
6) [Deploy Java application with Complete CI/CD pipeline Jenkins - Subversion, Jenkins, Tomcat](https://medium.com/@prashantsde/deploy-java-application-with-complete-ci-cd-pipeline-jenkins-21d210279794)
7) [Set up a build pipeline with Jenkins and Amazon ECS](https://aws.amazon.com/ko/blogs/devops/set-up-a-build-pipeline-with-jenkins-and-amazon-ecs/)
8) [Deploy Jenkins from Docker to AWS using ECS Fargate with Load Balancer](https://www.youtube.com/watch?v=ZhEGuDs6hR8)
9) 



8) [Gitlab Geo 구성하기](https://medium.com/ctc-mzc/gitlab-geo-%EA%B5%AC%EC%84%B1%ED%95%98%EA%B8%B0-%EB%B6%84%EC%84%9D-1-37cef8c440df)

# 5. AWS CodePipeline

1) [AWS CodePipeline을 활용해 CI/CD 적용하기](https://medium.com/ctc-mzc/aws-codepipeline%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%B4-ci-cd-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-bef43bed1346)


# 6. 기타

1) [M1 Mac에서 우분투 20.04 ARM 설치 - GUI 포함](https://sincerity.page/random/Random-How_to_install_Ubuntu20.04_in_M1/)
2) [How to run an Ubuntu Desktop virtual machine using VirtualBox 7](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#3-install-your-image)
3)  
