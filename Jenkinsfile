pipeline {
    agent { label 'docker' }
    stages {
        stage('Refresh role') {
            steps {
                sh 'yum install -y python3'
                sh 'yum install -y procps-ng'
                sh 'pip3 install boto3'
                sh 'python3 --version'
                sh 'nohup python3 -u aws_role_juggler.py > output.log &'
                sh 'aws cloudformation describe-stacks --stack-name s24-infinity-cluster-0-nodegroup-system'
                sh 'sleep 5'
                sh 'pkill -f aws_role_juggler.py'
                sh 'ls -lrt'
                sh 'cat output.log'
                }
            }
        }
    }