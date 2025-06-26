pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Run nginx') {
            steps {
                script {
                    sh 'docker version' // check Docker CLI works
                    sh 'docker stop nginx || true'
                    sh 'docker rm nginx || true'
                    sh 'docker run --name nginx -d -p 9000:80 nginx'
                }
            }
        }
    }
}
