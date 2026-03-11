pipeline {
    agent any

    stages {
        stage('Build Docker') {
            steps {
                sh 'cd user-service && docker build -t user-service .'
            }
        }
    }
}