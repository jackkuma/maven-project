pipeline {
    agent any
    tools{
        maven 'local maven'
    }
    
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo '開始建檔......'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}