pipeline {
    agent any

    environment {
        IMAGE = "saran0702/trend-app:latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/saran02-Git/Staticfiles-CICD.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t $IMAGE .'
            }
        }
        
        stage('Docker Login') {
            steps {
                sh 'docker login -u saran0702 -p YOUR_PASSWORD'
            }
        }
        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE'
            }
        }
    }
}
