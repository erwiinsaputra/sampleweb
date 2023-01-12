pipeline {
    agent any

    stages('Docker') {
        stage('Build'){
            steps{
            sh 'sudo docker build . -t erwiinsaputra/testing:$(git rev-parse --short HEAD)'
            }
        }
        stage('Push') {
            steps{
            sh 'sudo docker push erwiinsaputra/testing:$(git rev-parse --short HEAD)'
            }
        }
    }
}
