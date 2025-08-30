pipeline {
    agent any

    tools {
        nodejs "NodeJS"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AryaBhatt05/Jenkins_CICD.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deployment successful!'
            }
        }
    }

    post {
        failure {
            echo '❌ Build failed!'
        }
        success {
            echo '✅ Build succeeded!'
        }
    }
}
