pipeline {  

    agent any
        
    tools{
        maven "Maven"
    }
    stages {
        stage('Clone') {
            steps {
              git credentialsId: 'maven-web-app', url: 'https://github.com/yeswanthreddy778/maven-web-app.git'
            }
        }
    
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
         stage('Deployment'){
             steps{
             sshagent(['118f7682-084b-4472-94cf-9e12f013dddb']) {
                   sh 'scp -o StrictHostKeyChecking=no target/maven-web-app.war azadmin@10.0.0.4:/opt/tomcat/webapps/'


        }
    }
}
}  
}    
