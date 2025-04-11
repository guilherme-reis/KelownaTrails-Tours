pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = credentials('firebase-ci-token')
    }

    stages {
        stage('Build') {
            steps {
                echo 'No build step required for this static HTML project.'
            }
        }

        stage('Test') {
            steps {
                echo 'Manual testing only for this assignment.'
            }
        }

        stage('Staging') {
            steps {
                sh 'firebase deploy --only hosting:staging --project kelownatrails-tours'
            }
        }

        stage('Production') {
            when {
                branch 'main'
            }
            steps {
                sh 'firebase deploy --only hosting:production --project kelownatrails-tours'
            }
        }
    }
}
