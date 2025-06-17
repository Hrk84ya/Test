
pipeline {
    agent any
    environment{
        PATH = "/usr/local/bin:$PATH"
        DOCKER_PATH="/usr/local/bin/docker"
    }
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
        stage ('Docker version') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Build Image'){
            steps{
                sh "docker build -t hrk84ya/flask-cont:latest ."
                echo "Image build successful"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying"
            }
        }
    }
}
