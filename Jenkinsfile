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
		stage ('Code Test') {
		
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
	}
}
