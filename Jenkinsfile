pipeline{
agentany
    tools{
    maven 'maven'
    }

    stages{
    
        stage('git checkout'){
            steps{
            git branch: 'prod', url: 'https://github.com/davidrakesh1/maven-web-application.git'
            }
            }
 
        stage('build'){
            steps{
            sh "mvn clean package"'
            }
           }   
        stage('deploy'){
            steps{
            sshagent(['new1']) {
           sh 'scp -o stricthostchecking=no target*/.war ec2user@18.117.228.19:/opt/tomcat2/webapps/
            }
            }
           }   
        
    }
    }
