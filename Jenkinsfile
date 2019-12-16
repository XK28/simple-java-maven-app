node {
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarQubeScanner';
    withSonarQubeEnv('Sonarqube') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
