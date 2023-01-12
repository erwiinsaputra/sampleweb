pipeline {
    agent any

    stages('API') {
        stage('Build'){
            steps{
            sh 'sudo docker build . -t erwiinsaputra/testing:$(git rev-parse --short HEAD) \ 
            export IMAGES_NAME="erwiinsaputra/testing:$(git rev-parse --short HEAD) \ 
            envsubst < deployment.yaml.template > deployment.yaml'
            }
        }
        stage('Push') {
            steps{
            sh 'sudo docker push erwiinsaputra/testing:$(git rev-parse --short HEAD)'
            }
        }
        stage('Deploy Dev') {
            steps{
            build 'gke'
            }
        }
    }
}
