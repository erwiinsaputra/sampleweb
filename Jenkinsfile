pipeline {
    agent any

    stages('Docker') {
        stage('Build'){
            steps{
            sh 'docker build .'
            }
        }
    }
}
