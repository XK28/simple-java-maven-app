pipeline {
    agent any
    stages {
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('Sonarqube') {
                    
                        sh 'mvn sonar:sonar'
            
                }
            }
        }
       
    }
}
