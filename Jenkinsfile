pipeline {
    agent any
 
    environment {
        AWS_REGION = 'us-west-1' // Update with your desired region
        STACK_NAME = 'MyEC2Stack'
        TEMPLATE_FILE = './cfn-template/ec2-template.yaml'
    }
 
    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
git 'https://github.com/bobademayur/cloudformation.git' // Update with your repository URL
            }
        }
        stage('Deploy CloudFormation Stack') {
            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'aws_credentials']]) {
                    sh """
                    aws cloudformation deploy \
                        --template-file $TEMPLATE_FILE \
                        --stack-name $STACK_NAME \
                        --region $AWS_REGION \
                        --capabilities CAPABILITY_NAMED_IAM
                    """
                }
            }
        }
    }
}
