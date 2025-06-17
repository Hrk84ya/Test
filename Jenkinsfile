pipeline {
    agent any
    environment {
        DOCKER_USERNAME="hrk84ya"
        DOCKER_IMAGE="flask-img"
        DOCKER_CONTAINER="flask-cont"
        TAG="latest"
        FULL_PATH="${DOCKER_USERNAME}/${DOCKER_IMAGE}:${TAG}"
        PATH = "/usr/local/bin:$PATH"
        DOCKER_PATH="/usr/local/bin/docker"
    }
    stages {
        stage('Build') {
            steps {
                echo "Building"
            }
        }

        stage('Test') {
            steps {
                echo "Testing"
            }
        }

        stage('Build and Verify Docker') {
            parallel {
                stage('Docker version') {
                    steps {
                        sh 'docker --version'
                    }
                }
                stage('Build Image') {
                    steps {
                        sh "docker build -t ${FULL_PATH} ."
                        echo "Image build successful"
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh '''
                    existing_container=$(docker ps --filter "publish=8000" --format "{{.ID}}")
                    if [ -n "$existing_container" ]; then
                        echo "Stopping container using port 8000: $existing_container"
                        docker stop $existing_container
                    fi
                    '''
                    sh "docker run -d --rm --name ${DOCKER_CONTAINER} -p 8000:8000 ${FULL_PATH}"
                }
            }
        }
    }
}
