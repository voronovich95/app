pipeline {
    agent any
    stages {
        stage('Sent message about starting deploy') {
            steps {
                sh 'curl -s -X POST https://api.telegram.org/bot6061794557:AAG7GW-CCfu-z4hPZ5pffgOBgf4SGzhSvRw/sendMessage -d chat_id=-1001540507095 -d parse_mode="Markdown" -d text="Starting deployment by roman.voronovich"'
            }
        }
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
        
        stage('Sent message about finishing deploy') {
            steps {
                sh 'curl -s -X POST https://api.telegram.org/bot6061794557:AAG7GW-CCfu-z4hPZ5pffgOBgf4SGzhSvRw/sendMessage -d chat_id=-1001540507095 -d parse_mode="Markdown" -d text="Success deployment"'
            }
        }
    }
}
