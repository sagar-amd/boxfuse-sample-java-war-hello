pipeline 
{

  agent any

  environment 
{
      PATH = "/usr/share/:$PATH"
  }


  stages 

	{
      	stage("Get the code from git")
			{
          			steps
				{
            			git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
      			}
      		}

		stage("build the code")
			{
          			steps
				{
              			sh "mvn clean package"
          			}
      		}
      
		stage("deploy the code")
			{
      		    steps
				{
             			deploy adapters: [tomcat9(credentialsId: 'one11', path: '', url: 'http://54.157.146.95:8080/')], 
contextPath: 'myapp', onFailure: false, war: '**/*.war'          			
      			}
  	}		}
}
