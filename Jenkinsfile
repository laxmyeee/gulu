pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out the project...'
                checkout scm
            }
        }

        stage('Check Project') {
            steps {
                echo 'Checking project files...'
                bat 'dir'
                bat 'dir backend'
                bat 'dir frontend'
            }
        }

        stage('Backend') {
            steps {
                echo 'Checking backend...'
                bat 'cd backend && dir'
            }
        }

        stage('Frontend') {
            steps {
                echo 'Checking frontend...'
                bat 'cd frontend && dir'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage completed.'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage completed.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the Console Output.'
        }
    }
}