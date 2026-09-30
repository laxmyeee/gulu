pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Running build phase...'
                bat 'cd frontend && npm install'
                bat 'cd frontend && npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test phase...'
                bat 'cd frontend && npm run lint'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
            cleanWs()
        }

        success {
            echo 'Build and tests completed successfully.'
        }

        failure {
            echo 'Build or tests failed.'
        }
    }
}