pipeline {
    agent any
    tools{
        maven 'local maven'
    }
    
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
                bat "/Users/user/local/bin/docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}