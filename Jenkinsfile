pipeline
{
	agent any
	{
	{
		stage ('SCM Checkout') {
		git 'https://github.com/vgurunani/maven-project.git'
		}
	}	
	{
		stage ('Code Test') {
		withMaven(maven: 'LocalMaven') {
			sh 'mvn test'
			}
		}
	}
	}
}
