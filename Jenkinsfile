pipeline {
    agent any
    tools{
        maven 'local maven'
    }
    
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
                bat "/usr/local/bin/docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}