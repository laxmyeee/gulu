pipeline {
    agent any

    stages {

        stage('Flutter Doctor') {
            steps {
                bat 'flutter doctor -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }

        stage('Analyze') {
            steps {
                bat 'flutter analyze'
            }
        }

        stage('Test') {
            steps {
                bat 'flutter test'
            }
        }

        stage('Build APK') {
            steps {
                bat 'flutter build apk --release'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build\\app\\outputs\\flutter-apk\\app-release.apk',
                             allowEmptyArchive: true
        }

        success {
            echo 'Flutter project built and tested successfully!'
        }

        failure {
            echo 'Build or test failed. Check the console output.'
        }
    }
}