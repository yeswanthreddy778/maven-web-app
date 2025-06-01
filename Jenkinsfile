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
                 sshagent(['c0dc0dfc-c5d7-4a73-8528-ae04bba4dc48']) {
                   sh 'scp -o StrictHostKeyChecking=no target/maven-web-app.war azadmin@10.0.0.4:/home/azadmin/apache-tomcat-9.0.105/webapps/'

        }
    }
}
}  
}    
