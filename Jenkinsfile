node {
  stage('SCM') {
    git 'https://github.com/NekoNoName/simple-java-maven-app.git'
  }
  stage('SonarQube analysis') {
    withSonarQubeEnv() { // Will pick the global server connection you have configured
      sh './gradlew sonarqube'
    }
  }
}
