pipeline {
    agent none
    stages {
        stage('test') {
            environment { 
                TEST_ENV = 'THIS IS TEST VAR'
            }
            steps {
                sh 'printenv'
                // timeout(time: 1, unit: 'MINUTES') {
                //     retry(5) {
                //         sh 'date'
                //     }
                // }
            }
        }
        stage('Back-end') {
            agent {
                docker { image 'bash:latest' }
            }
            steps {
                sh 'ls -la'
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
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
