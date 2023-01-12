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
        stage('Versioning') {
            steps{
            sh 'export IMAGES_NAME=erwiinsaputra/testing:$(git rev-parse --short HEAD)'
            }
        }
        stage('Update') {
            steps{
            sh 'envsubst < deployment.yaml.template > deployment.yaml'
            }
        }
        stage('Deploy Dev') {
            steps{
            build 'gke'
            }
        }
    }
}
