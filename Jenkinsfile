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
        stage('Auth') {
            steps{
            sh 'gcloud container clusters get-credentials cluster-survei-io --zone asia-southeast2-a --project survei-io-development'
            }
        }
        stage('Deploy Dev') {
            steps{
            build 'gke'
            }
        }
    }
}
