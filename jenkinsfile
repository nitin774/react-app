pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token')
    }

    stages {
        stage('install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests...'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('deploy') {
            steps {
                bat "npx vercel --prod --yes --token=%VERCEL_TOKEN%"
            }
        }
    }
}
