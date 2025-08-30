pipeline {
    agent any   // run on any available Jenkins agent

    tools {
        nodejs "NodeJS"   // Name of the NodeJS installation in Jenkins (Manage Jenkins > Global Tool Configuration)
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AryaBhatt05/Jenkins_CICD.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'   // use 'bat' on Windows if no NodeJS plugin is configured
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'      // runs your test suite
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build' // optional: only if you have a build script in package.json
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // add deployment steps here (copy files, docker, ssh, etc.)
            }
        }
    }

    post {
        success {
            echo '✅ Build succeeded!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
