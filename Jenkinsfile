pipeline {
    
    agent any
    triggers{
    pollSCM('* * * * *')
    }
    stages {
        stage('VCS') {
            steps {
                git branch: 'main', url: 'https://github.com/Saleor-workshop/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t aegonn/saleor-dashboard:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker push aegonn/saleor-dashboard:DEV'
            }
        }
    }
}
