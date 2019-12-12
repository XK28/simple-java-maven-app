node {
  stage('SCM') {
    git 'https://github.com/NekoNoName/simple-java-maven-app.git'
  }
  stage('SonarQube analysis') {
     def mvnHome =  tool name: 'maven-3', type: 'maven' 
        withSonarQubeEnv('GLW SonarQube Server') { 
             sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
}
