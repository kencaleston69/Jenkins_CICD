pipeline {
    agent {
        label 'app01'
    }

    stages {
        stage('Build') {
            steps {
                git branch: "master",
                url: 'http://git.stratos.xfusioncorp.com/sarah/web.git'

                sh 'docker build -t stregi01.stratos.xfusioncorp.com:5000/nginx:latest .'
                sh 'docker push stregi01.stratos.xfusioncorp.com:5000/nginx:latest'
            }
        }
    }
}