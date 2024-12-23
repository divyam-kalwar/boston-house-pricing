pipeline {
    agent any

    environment {
        IMAGE_NAME = "your-dockerhub-username/streamlit-app"
        PORT = 8501
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ${IMAGE_NAME} .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-credentials-id', url: '']) {
                    sh 'docker push ${IMAGE_NAME}'
                }
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p ${PORT}:${PORT} --name streamlit-app ${IMAGE_NAME}'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
