@Library('jenkins-shared-library') _ 
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
                buildImage()
            }
        }
	stage('Docker Login') {
            steps {
                withCredentials([
                    usernamePassword(
                        credentialsId: '7d4c4226-a58d-4c55-8723-3dc73985bb72',
                        usernameVariable: 'DOCKER_USER',
                        passwordVariable: 'DOCKER_PASS'
                    )
                ]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }
        stage('push image on docker hub') {
            steps {
		sh 'docker tag jenkins-demo:v1 chitranshjangra23/jenkins-demo:v1'
                sh 'docker push chitranshjangra23/jenkins-demo:v1'
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
