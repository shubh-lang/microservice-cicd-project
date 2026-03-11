pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/shubh-lang/microservice-cicd-project.git'
            }
        }

        stage('Build Docker') {
            steps {
                sh 'cd user-service && docker build -t user-service .'
            }
        }
    }
}