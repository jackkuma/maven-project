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

        stage('Deploy to staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }

        stage('Deploy to Production'){
            steps {
                timeout(time:5, unit:'DAYS'){
                    input message:'是否佈署到正式環境?'
                }

                build job: 'deploy-to-production'
            }
            post {
               success {
                   echo '代碼成功佈署到正式環境'
               }

               failure {
                   echo '佈署失敗'
               }
            }
        }
    }
}