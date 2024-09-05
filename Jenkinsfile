pipeline {
    agent any

    environment {
        // Define environment variables here (optional)
        DEPLOY_SERVER = 'jyothirk@52.91.86.30'
        //DEPLOY_PATH = '/var/www/sample-app'
    }


    stages {
        stage('Clone') {
            steps {
                // Clone the repository
                git branch: 'main', url: "https://github.com/Jyothidk/gravity-task2.git"
            }
        }

        stage('Deploy') {
            steps {
                // Deploy 2048 code to the server
                sh """
                sudo rm -rf /usr/share/nginx/html/index.html
                sudo cp 2048 /usr/share/nginx/html
                
                """
            }
        }
    }
}

