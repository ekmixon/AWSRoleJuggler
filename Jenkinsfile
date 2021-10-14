pipeline {
    agent { label 'docker' }
    stages {
        stage('Refresh role') {
            steps {
                sh 'yum install -y python3'
                sh 'pip3 install boto3'
                sh 'python3 --version'
                sh 'python3 aws_role_juggler.py -r arn:aws:iam::728137396354:role/fizz-deploy-role'
                }
            }
        }
    }