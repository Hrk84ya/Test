pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'docker build -t myapp:latest .'
                sh 'docker run -d -p 8080:8080 myapp:latest'
            }
        }
    }
}