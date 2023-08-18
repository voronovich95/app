pipeline {
    agent any
    stages {
        stage('Build image') {
            steps {
               script {
                    docker.build('my_app.01')
                }
            }
        }
        stage('Recretate container') {
            steps {
                sh 'docker compose up -d --force-recreate'
            }
        }

        stage('Test') {
            steps {
                sh 'curl 192.168.122.34:80'
            }
        }
    }
}
