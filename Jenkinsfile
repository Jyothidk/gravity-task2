pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                // Clone the repository
                git branch: 'main', url: "https://github.com/Jyothidk/gravity-task2.git"
                // Present Working directory
                sh "pwd"
                }
            }
        stage('Deploy') {
            steps {
                // Deploy 2048 code 
                sh """
                sudo cp -r 2048 /var/www/html/
                
                """
            }
        }
       
    }
}

