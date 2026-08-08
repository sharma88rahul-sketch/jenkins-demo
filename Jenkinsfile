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

        stage('push image on docker hub') {
            steps {
                sh 'docker push rahuldevops/jenkins-demo:v1'
            }
        }
	stage('buld the image'){
	    steps {
		sh "docker rm -f app || true"
		sh "docker run -d --name app -p 8081:80 jenkins-demo:v1"
	    }
	}
    }
}
