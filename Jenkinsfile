pipeline {
    agent any
    
    environment {
        // Define your SSH credentials here
        SSH_KEY = credentials('server-key2')
        SSH_USER = 'ubuntu'
        REMOTE_HOST = '54.237.94.30'
        REMOTE_PATH = '/var/www/'
    }
    
    stages {
        stage('Install Dependencies') {
            steps {
                //sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
              //  sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    // Transfer build artifacts using rsync over SSH
                    sshagent(['jenkins-ssh']) {
                        sh "cd /var/lib/"
                        //sh "rsync -avz -e 'ssh -i server-key.pem' build/ ${SSH_USER}@${REMOTE_HOST}:${REMOTE_PATH}"
                        sh "ls -la"
                    }

                }
            }
        }
    }
}