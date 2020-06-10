pipeline {
    agent any
    stages{
<<<<<<< HEAD
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo '開始建檔......'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
=======
        stage('Init'){
            steps {
                echo "Testing......"
            }
        }
 	stage('Build'){
            steps {
                echo "Building......"
            }
        }
 	stage('Deploy'){
            steps {
                echo "Code Deployed."
>>>>>>> 81ee40b5734c60561ccb5c58dd62b8b06974d063
            }
        }
    }
}