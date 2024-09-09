pipeline {
    agent any
    
    environment {
        GIT_REPO_URL = 'https://github.com/Jyothidk/gravity-task2.git'
        
        TARGET_SERVER = '3.75.171.240' 
        DEPLOY_PATH = '/var/www/html/'
        SSH_CREDENTIALS_ID = 'ssh-id' 
    }
    stages {
        stage('Clone') {
            steps {
                // Clone the repository
                git branch: 'main', url: "${env.GIT_REPO_URL}"
                // Present Working directory
                sh "pwd"
                }
            }
      stage('Deploy') {
            steps {
                script {
                    // Use SSH agent to handle SSH authentication
                    sshagent([env.SSH_CREDENTIALS_ID]) {
                        sh """
                        # Copy files to the target server
                        #scp -i /home/ubuntu/.ssh/jenkins_key -r 2048 ubuntu@3.75.171.240:/var/www/html/
                        #scp -o StrictHostKeyChecking=no -r ./* ${TARGET_SERVER}:${DEPLOY_PATH}
                        
                        scp -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/jenkins_key -r 2048 ubuntu@${TARGET_SERVER}:${DEPLOY_PATH}
                        ssh -i /var/lib/jenkins/.ssh/jenkins_key -o StrictHostKeyChecking=no ubuntu@${TARGET_SERVER} 'sudo systemctl restart nginx'
                        """
                       
                    }
                }
            }
        }


        
    }
}

