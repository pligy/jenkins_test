pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/pligy/jenkins_test.git']])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/pligy/jenkins_test.git'
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