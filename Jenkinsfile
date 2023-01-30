pipeline {

  agent any
  environment {
      PATH = "/usr/share/:$PATH"
  }
 
 stages {
      stage("Get the code from git"){
          steps{
            git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
          
          }
      }
      stage("build the code"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy code in tomcat"){
          steps{
              deploy adapters: [tomcat9(credentialsId: '4a4df800-f614-47e6-ae1c-27a024eaac0d', path: '', url: 'http://54.236.53.175:8080')], contextPath: 'Harish', war: '**/*.war'
          }
      }
  }
}
