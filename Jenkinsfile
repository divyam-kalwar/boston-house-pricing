pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "house-price-prediction"
        DOCKER_TAG = "latest"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the Git repository
                git 'https://github.com/divyam-kalwar/boston-house-pricing.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    sh "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
                }
            }
        }

        stage('Test Docker Image') {
            steps {
                script {
                    // Run the Docker container to test it
                    sh "docker run -d -p 5000:5000 ${DOCKER_IMAGE}:${DOCKER_TAG}"
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    // Log in to Docker Hub
                    sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
                    
                    // Tag the image with Docker Hub repository and push
                    sh "docker tag ${DOCKER_IMAGE}:${DOCKER_TAG} your-dockerhub-username/${DOCKER_IMAGE}:${DOCKER_TAG}"
                    sh "docker push your-dockerhub-username/${DOCKER_IMAGE}:${DOCKER_TAG}"
                }
            }
        }

        stage('Deploy to Streamlit') {
            steps {
                script {
                    // Deploy to Streamlit (assuming you have Streamlit sharing or other deployment methods)
                    sh "streamlit share your-dockerhub-username/${DOCKER_IMAGE}:${DOCKER_TAG}"
                }
            }
        }
    }

    post {
        always {
            // Clean up the docker containers after pipeline completion
            sh "docker system prune -f"
        }
    }
}
