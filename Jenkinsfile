node {
  stage('SCM') {
    git 'https://github.com/NekoNoName/simple-java-maven-app.git'
  }
  stage('SonarQube analysis') {
     ef scannerHome = tool 'GLW Sonar Scanner; 
        withSonarQubeEnv('GLW SonarQube Server') { 
             sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
}
