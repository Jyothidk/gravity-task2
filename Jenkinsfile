pipeline {
    agent any

    environment {
        // Define environment variables here (optional)
        REPO_URL = 'https://github.com/Jyothidk/gravity-task2.git'
        //DEPLOY_SERVER = 'user@your-server.com'
        //DEPLOY_PATH = '/var/www/sample-app'
    }

    stages {
        stage('Clone') {
            steps {
                // Clone the repository
                git branch: 'main', url: "${REPO_URL}"
            }
        }














}