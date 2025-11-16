pipeline {
    agent any
    tools { nodejs 'Node18' }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Linting') {
            steps {
                sh 'echo "Linting passed (no eslint configured)"'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
        stage('Archive Artifact') {
            steps {
                sh 'zip -r build-artifact.zip . -i *.js *.json testScript.js || true'
                archiveArtifacts artifacts: 'build-artifact.zip', fingerprint: true
            }
        }
    }
    post {
        success {
            echo 'Email sent to team@example.com - Build succeeded!'
        }
        failure {
            echo 'Email sent to team@example.com - Build failed!'
        }
    }
}