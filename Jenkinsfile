pipeline {
    agent any

    stages('Docker') {
        stage('Login'){
            step{
            sh '/home/script/dockerlogin.sh'
            }
        }
    }
}
