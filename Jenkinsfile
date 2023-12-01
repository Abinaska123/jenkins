pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="591481069844"
        AWS_DEFAULT_REGION="eu-north-1"
        IMAGE_REPO_NAME="laravelimage"
        IMAGE_REPO_NAME2="sqlimage"
        IMAGE_TAG="latest"
        REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"
        REPOSITORY_URI2 = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME2}"
    }
   
    stages {
        
         stage('Logging into AWS ECR') {
            steps {
                script {
                sh "aws ecr get-login-password --region ${AWS_DEFAULT_REGION} | docker login --username AWS --password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"
                }
                 
            }
        }
    }
}
