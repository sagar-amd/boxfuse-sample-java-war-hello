pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  stages {
      stage("git"){
          steps{
            git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
          
          }
      }
      stage("build"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'TOMCAT004CREDENTIALS', path: '', url: 'http://15.207.222.78:8080/')], contextPath: 'sample', war: '**/*.war'
          }
      }
  }
}
