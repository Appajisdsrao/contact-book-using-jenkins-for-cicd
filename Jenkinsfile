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
                    sh 'docker build -t contact-book-backend -f Backend/Dockerfile Backend/'
                    sh 'docker build -t contact-book-frontend -f frontend/Dockerfile frontend/'
                }
            }
        }
        stage('Run Containers') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 --name backend contact-book-backend'
                    sh 'docker run -d -p 3000:3000 --name frontend contact-book-frontend'
                }
            }
        }
    }
}
