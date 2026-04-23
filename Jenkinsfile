pipeline {
    agent any

    environment {
        IMAGE = "saran0702/trend-app:latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/saran02-Git/Staticfiles-CICD.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t $IMAGE .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE'
            }
        }
    }
}
