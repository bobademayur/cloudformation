pipeline{
    agent any
    stages {
        stage('submit stack') {
            steps {
                sh "aws cloudformation create-stack --stack-name MyStack --template-body file://asg.yaml --region 'us-east-1'"
            }
        }

    }
}