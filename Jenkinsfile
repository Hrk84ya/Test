
pipeline {
    agent any
    environment{
        DOCKER_USERNAME="hrk84ya"
        DOCKER_IMAGE="flask-cont"
        TAG="latest"
        FULL_PATH="${DOCKER_USERNAME}/${DOCKER_IMAGE}:${TAG}"
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
                sh "docker build -t ${DOCKER_USERNAME}/${DOCKER_IMAGE}:latest ."
                echo "Image build successful"
            }
        }
        stage('Deploy'){
            steps{
                sh "docker run -d --rm -p 8000:8000 ${FULL_PATH}"
            }
        }
    }
}
