 pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'master', url: 'https://github.com/srinfotech7358/onlinebookstore.git'
            }
        }
        
          stage('Build') {
            steps {
               bat 'mvn clean install'
            }
        }
         stage('Generate Artifacts') {
            steps {
               archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }

          stage('Deploy to Tomcat Server') {
            steps {
               deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'Tomcat', path: '', url: 'http://localhost:8080')], contextPath: 'SR INFOTECH SOLUTIONS PVT LIMITED', war: 'target/*.war'
            }
        }
    }
}