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
                sh  'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('Verify Image') {
            steps {
                sh 'docker images'
            }
        }
	stage('buld the image'){
	    steps{
		sh "docker rm -d app || true"
		sh "docker run -d --name app -p 8080:80 jenkins-demo:v1"
    }
}
