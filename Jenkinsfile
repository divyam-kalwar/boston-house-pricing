pipeline {
    agent any

    environment {
        IMAGE_NAME = "divyam98/streamlit-app"
        PORT = "8501"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/divyam-kalwar/boston-house-pricing.git',
                    credentialsId: 'github-token' // Add your GitHub credentials ID here
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t ${IMAGE_NAME} .'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-credentials-id', url: 'https://index.docker.io/v1/']) {
                    sh 'docker push ${IMAGE_NAME}'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh '''
                        docker stop streamlit-app || true
                        docker rm streamlit-app || true
                        docker run -d -p ${PORT}:${PORT} --name streamlit-app ${IMAGE_NAME}
                    '''
                }
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
