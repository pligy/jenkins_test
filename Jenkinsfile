pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'python main.py'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'main.py', onlyIfSuccessful: true
            }
        }
    }
}