pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git url: 'https://github.com/NekoNoName/simple-java-maven-app.git'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('GLW SonarQube Server') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.5') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
        stage("Quality Gate") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    // Parameter indicates whether to set pipeline to UNSTABLE if Quality Gate fails
                    // true = set pipeline to UNSTABLE, false = don't
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}
