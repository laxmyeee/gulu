pipeline {
    agent any

    environment {
        PATH = "C:\\src\\flutter\\bin;${env.PATH}"
    }

    stages {

        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Flutter Version') {
            steps {
                bat 'flutter --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }

        stage('Test') {
            steps {
                bat 'flutter test'
            }
        }
    }
}