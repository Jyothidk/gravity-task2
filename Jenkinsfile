pipeline {
    agent any

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
                rm -rf /usr/share/nginx/html/index.html
                cp 2048 /usr/share/nginx/html
                
                """
            }
        }
    }
}

