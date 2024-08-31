pipeline {
    agent any
    stages {
        stage('Pull') {
            steps {
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kencaleston69/Jenkins_CICD.git']])      
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t ken_pipe .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker rm -f web-nginx && docker run -d --name web-nginx -p 8083:80 ken_pipe'
            }
        }
    }
}
