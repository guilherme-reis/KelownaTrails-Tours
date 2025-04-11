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
                sh 'firebase use staging'
                sh 'firebase deploy --only hosting'
            }
        }

        stage('Production') {
            when {
                branch 'main'
            }
            steps {
                sh 'firebase use production'
                sh 'firebase deploy --only hosting'
            }
        }
    }
}
