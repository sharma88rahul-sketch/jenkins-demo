pipeline {
    agent any

    tools {
        sonarQubeScanner 'sonar-scanner'
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/sharma88rahul-sketch/jenkins-demo.git'
            }
        }

        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('sonar') {
                    sh '''
                    sonar-scanner \
                    -Dsonar.projectKey=jenkins-demo \
                    -Dsonar.sources=.
                    '''
                }
            }
        }
    }
}
