pipeline {
    agent any

    stages('Docker') {
        stage('Login'){
            steps{
            sh '/home/script/dockerlogin.sh'
            }
        }
    }
}
