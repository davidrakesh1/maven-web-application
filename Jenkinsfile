pipeline{
agent any 
tools {
    maven 'maven'
}
    
    triggers{
    pollSCM(* * * * *)
    }
    
stages{
    
    stage('code checkout'){
        steps{
          git branch: 'qa', url: 'https://github.com/davidrakesh1/maven-web-application.git'
  }
  }
 
    stage('build'){
        steps{
            sh 'mvn clean package'
  }
  }

  stage('deploy to tomcat'){
        steps{
           sshagent(['new1']) {
         sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@18.220.217.117:/opt/tomcat3/webapps/' 
    
  }
  }
  }
  
  
}
}
