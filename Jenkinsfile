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
              git branch: 'dev', url: 'https://github.com/davidrakesh1/maven-web-application.git'			}
		}
	}
		
		stage('build'){
			steps{
			sh "mvn clean package"	
			}
		}	
	
	stage('deploy'){
		steps{
		sshagent(['tomcat2']) {
                sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@18.117.228.19:/opt/tomcat2/webapps'  
          }
	}
	}
				
}

