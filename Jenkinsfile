pipeline {
    agent any

    stages {
        stage('Debug Files') {
            steps {
                sh 'ls -R'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t backend-app ./backend'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f backend-container || true'
                sh 'docker run -d --name backend-container backend-app'
            }
        }
    }
}
