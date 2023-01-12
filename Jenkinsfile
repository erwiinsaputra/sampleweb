pipeline {
    agent any

    stages('Docker') {
        stage('Login'){
            steps{
            sh '~/script/dockerlogin.sh'
            }
        }
    }
}
