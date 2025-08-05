pipeline {
    agent any

    environment {
        // Define a unique image name for each build
        IMAGE_NAME = "nodejs-demo-app:${env.BUILD_NUMBER}"
        // Placeholder for the Docker registry URL.
        // In a real Jenkins setup, this would be a configured variable.
        REGISTRY_URL = "your-registry-url/your-username/${IMAGE_NAME}"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building Docker image: ${IMAGE_NAME}"
                // Build the Docker image from the Dockerfile in the current directory
                sh "docker build -t ${IMAGE_NAME} ."
            }
        }

        stage('Test') {
            steps {
                echo "Testing application..."
                // Run the container in detached mode and expose port 8080
                sh "docker run -d --name test-container -p 8080:8080 ${IMAGE_NAME}"

                // Give the app a moment to start up
                sh "sleep 5"

                // Use curl to check if the app is running and returns the correct response
                sh 'curl http://localhost:8080/ | grep "Hello World!"'
            }
        }

        stage('Deploy') {
            steps {
                echo "Logging in to Docker registry..."
                // This is a placeholder for logging into a Docker registry.
                // In a real pipeline, you would use Jenkins's withCredentials wrapper
                // to securely handle credentials.
                // e.g., withCredentials([string(credentialsId: 'my-docker-credentials', variable: 'DOCKER_PASSWORD')]) {
                //   sh "echo ${DOCKER_PASSWORD} | docker login -u my-docker-user --password-stdin"
                // }

                echo "Tagging image for deployment: ${REGISTRY_URL}"
                sh "docker tag ${IMAGE_NAME} ${REGISTRY_URL}"

                echo "Pushing image to registry..."
                sh "docker push ${REGISTRY_URL}"
            }
        }
    }

    post {
        always {
            // This block runs after all stages, regardless of the outcome
            echo "Cleaning up..."
            // Stop and remove the test container if it exists
            sh "docker stop test-container || true"
            sh "docker rm test-container || true"
        }
    }
}
