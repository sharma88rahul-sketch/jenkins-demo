pipeline {
    agent any

    stages {
        stage('Check Sonar Tool') {
            steps {
                script {
                    def scannerHome = tool 'sonar-scanner'
                    echo "Scanner Home: ${scannerHome}"
                }
            }
        }
    }
}
