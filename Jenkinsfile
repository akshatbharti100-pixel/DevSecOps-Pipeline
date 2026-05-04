pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/akshatbharti100-pixel/DevSecOps-Pipeline.git'
            }
        }
        stage('Security Scan (Trivy)') {
            steps {
                echo 'Running vulnerability scan...'
                sh 'trivy fs .'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t devsecops-final-app:${BUILD_NUMBER} .'
            }
        }
    }
}
