pipeline{
    agent any
    stages {
        stage('submit stack') {
            steps {
                sh "aws cloudformation create-stack --stack-name MyStack --template-body file://ec2cft.yaml --region 'us-east-1'"
            }
        }

    }
}