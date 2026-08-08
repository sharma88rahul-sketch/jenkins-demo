pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning Source Code'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('Verify Image') {
            steps {
                bat 'docker images'
            }
        }

    }
}
