stage('Sonarqube') {
    environment {
        scannerHome = tool 'GLW SonarQube Scanner'
    }
    steps {
        withSonarQubeEnv('GLW SonarQube Server') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}
