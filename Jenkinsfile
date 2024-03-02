pipeline {
    agent {
        docker { image 'python:latest' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'python main.py'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'main.py', onlyIfSuccessful: true
            }
        }
    }
}