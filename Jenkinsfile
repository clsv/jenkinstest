pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'bash:latest' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'ubuntu:latest' }
            }
            steps {
                sh 'lsb_release -a'
            }
        }
    }
}