pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Appajisdsrao/contact-book-using-jenkins-for-cicd.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    // Build backend
                    sh 'docker build -t contact-book-backend -f backend/Dockerfile backend/'

                    // Build frontend
                    sh 'docker build -t contact-book-frontend -f frontend/Dockerfile frontend/'
                }
            }
        }

        stage('Run Containers') {
            steps {
                script {
                    // Start backend
                    sh 'docker run -d -p 5000:5000 --name backend contact-book-backend'

                    // Start frontend (assuming it runs on port 3000)
                    sh 'docker run -d -p 3000:3000 --name frontend --link backend contact-book-frontend'
                }
            }
        }
    }
}
