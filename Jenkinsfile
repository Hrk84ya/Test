pipeline {
    agent any

    environment {
        APP_PORT = '8000'
    }

    stages {
        stage('Clone repository') {
            steps {
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Run App') {
            steps {
                sh '''
                    nohup python app.py &
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
