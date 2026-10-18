pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arpan050/jenkins-docker.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f jenkins-demo-container || true'
                sh 'docker run -d --name jenkins-demo-container -p 3000:3000 jenkins-demo-app'
            }
        }
    }
}
