pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'your-dockerhub-username/app-name'
    }
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Rushikesh0020/JenkinsPractice'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Push Docker Image') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }
    }
}