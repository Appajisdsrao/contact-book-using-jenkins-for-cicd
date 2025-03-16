pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url: 'https://github.com/Appajisdsrao/contact-book-using-jenkins-for-cicd.git'
            }
        }
        stage('Build') {
            steps {
                // Add any build steps, like compiling, running tests, etc.
                echo 'Building the project...'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the application to the desired environment
                echo 'Deploying the project...'
            }
        }
    }
}
