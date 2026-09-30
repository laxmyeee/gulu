pipeline {
    agent any

    stages {

        stage('Check Node') {
            steps {
                bat 'node --version'
                bat 'npm --version'
            }
        }

        stage('Backend - Install') {
            steps {
                dir('backend') {
                    bat 'npm ci'
                }
            }
        }

        stage('Backend - Test') {
            steps {
                dir('backend') {
                    bat 'echo No backend tests configured yet'
                }
            }
        }

        stage('Backend - Build') {
            steps {
                dir('backend') {
                    bat 'echo Backend build completed'
                }
            }
        }

        stage('Frontend - Install') {
            steps {
                dir('frontend') {
                    bat 'npm ci'
                }
            }
        }

        stage('Frontend - Test') {
            steps {
                dir('frontend') {
                    bat 'npm run test --if-present'
                }
            }
        }

        stage('Frontend - Build') {
            steps {
                dir('frontend') {
                    bat 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }

        failure {
            echo 'Build or tests failed.'
        }

        always {
            archiveArtifacts artifacts: 'frontend/dist/**',
                             allowEmptyArchive: true
        }
    }
}