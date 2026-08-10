pipeline {
    agent any

    stages {

        stage('Check Sonar') {
            steps {
                sh 'which sonar-scanner || true'
                sh 'sonar-scanner --version || true'
            }
        }
    }
}
