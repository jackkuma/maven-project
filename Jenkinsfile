pipeline {
    agent any
    tools{
        maven 'local maven'
    }
    
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
            post {
                success {
                    echo '開始建檔......'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }

    stages{
        stage('Deploy to staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}