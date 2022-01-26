pipeline{
	agent any
	tools{
	maven 'maven'
	}
	triggers{
	pollSCM('* * * * *')
	}
	stages{
		stage('checkout'){
			steps{
		git 'https://github.com/davidrakesh1/maven-web-application.git'	
			}
		}
		
	}
	
	
}
