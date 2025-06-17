pipeline {
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Building"
            }
        }
        stage('Test'){
            steps{
                echo "Testing"
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t hrk84ya/flask-cont:latest .'
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying"
            }
        }
    }
}
