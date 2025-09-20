pipeline {
    agent any

    tools {
        maven 'maven3'   // This should match the Maven name you added in Jenkins Tools
        jdk 'jdk17'     // If you installed JDK in Jenkins Tools, give its name
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/RakshithAjila/java-webapp-project.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }
}
