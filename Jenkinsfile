pipeline {
    agent any

    stages('Docker') {
        stage('Build'){
            steps{
            sh 'Docker build . -t'
            }
        }
    }
}
