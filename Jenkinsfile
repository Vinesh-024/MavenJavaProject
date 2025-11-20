pipeline {
    agent any

    tools {
        maven 'Maven-Home'       // Jenkins → Global Tool Configuration
        jdk 'JDK'            // Jenkins → Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/Vinesh-024/MavenJavaProject.git',
                    credentialsId: 'github-token'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests=false'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
