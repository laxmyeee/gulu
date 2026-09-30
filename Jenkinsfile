pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'cd frontend && npm install'
            }
        }

        stage('Lint') {
            steps {
                bat 'cd frontend && npm run lint'
            }
        }

        stage('Build') {
            steps {
                bat 'cd frontend && npm run build'
            }
        }
    }
}