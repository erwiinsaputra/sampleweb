pipeline {
    agent any

    stages('Docker') {
        stage('Build'){
            steps{
            sh 'sudo su | docker build .'
            }
        }
    }
}
