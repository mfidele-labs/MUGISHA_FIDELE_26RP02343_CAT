
pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    environment {
        CYPRESS_INSTALL_BINARY = '0'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check Environment') {
            steps {
                sh 'echo "Node.js version:"'
                sh 'node --version'
                sh 'echo "npm version:"'
                sh 'npm --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install --no-audit --no-fund'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}
