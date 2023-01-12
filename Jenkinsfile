pipeline {
    agent any

    stages('API') {
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
        stage('Deploy Dev') {
            steps{
            sh 'sudo kubectl apply -f ./deployment.yaml -n default'
            }
        }
}
