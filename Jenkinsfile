pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }
    post {
        success {
            echo 'Build and tests successful!'
        }
        failure {
            echo 'Build failed or tests failed!'
        }
    }
}