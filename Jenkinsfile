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
        stage('Deploy'){
            steps{
                echo "Deploying"
            }
        }
    }
}
