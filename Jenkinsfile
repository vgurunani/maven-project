pipeline
{
	agent any
	
	stages
	{
	
		stage ('SCM Checkout') {
			git 'https://github.com/vgurunani/maven-project.git'
		}
	}	
	{
		stage ('code test') {
		
		steps{
			withMaven(maven: 'LocalMaven') 
				{
				sh 'mvn test'
				}
			}
		}
		stage ('code build') {
		
		steps{
			withMaven(maven: 'LocalMaven')
				{
				sh 'mvn install'
				}
			}
		}
		

		stage('deploy to tomcat'){

		steps 
		 {
		  sshagent (['172.31.37.124']) {
			sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.37.124:/var/lib/tomcat/webapps'
				}
			}
		}
	}
}
