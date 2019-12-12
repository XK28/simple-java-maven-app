node {
  stage('SCM') {
    git 'https://github.com/NekoNoName/simple-java-maven-app.git'
  }
  stage('SonarQube analysis') {
     def scannerHome = tool 'GLW SonarQube Scanner
        withSonarQubeEnv('GLW SonarQube Server') { 
             sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
}
