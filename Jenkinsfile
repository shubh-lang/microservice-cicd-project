pipeline {
    agent any

    environment {
        IMAGE_NAME = "shubhankar230204/user-service"
    }

    stages {
        stage('Build Docker') {
            steps {
                sh 'cd user-service && docker build -t $IMAGE_NAME .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                    sh '''
                    docker login -u $USER -p $PASS
                    docker push $IMAGE_NAME
                    '''
                }
            }
        }
    }
}