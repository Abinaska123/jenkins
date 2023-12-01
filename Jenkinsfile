pipeline {
    agent any
    environment {
        AWS_DEFAULT_REGION = 'eu-north-1'  // Replace with your AWS region
        AWS_ACCOUNT_ID = '591481069844'     // Replace with your AWS account ID
        DOCKER_REGISTRY_URL = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"
        DOCKER_IMAGE_NAME = "docker-laravel-laravel-app"
        DOCKER_IMAGE_TAG = "latest"
        //DOCKER_COMPOSE_FILE = 'docker-compose.yml'
        //DOCKERFILE_PATH = 'docker/php/Dockerfile'
        DOCKER_IMAGE_NAMENGNIX = "docker-laravel-nginx"
    }
   
    stages {
        
         stage('Logging into AWS ECR') {
            steps {
                script {
                sh "sudo aws ecr get-login-password --region ${AWS_DEFAULT_REGION} | docker login --username AWS --password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"
                }
                 
            }
        }
    }
}
