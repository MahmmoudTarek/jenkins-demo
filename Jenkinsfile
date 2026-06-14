pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'docker build -t myapp:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f myapp || true
                docker run -d \
                  --name myapp \
                  -p 8080:80 \
                  myapp:v1
                '''
            }
        }

    }
}
