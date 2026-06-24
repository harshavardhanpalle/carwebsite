pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-creds',
                    url: 'https://github.com/harshavardhanpalle/carwebsite.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the carwebsite application...'
                sh 'ls -la'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to EC2...'
                sh 'sudo cp -r * /var/www/html/'
            }
        }
    }

    post {
        success { echo 'Pipeline completed successfully!' }
        failure { echo 'Pipeline failed. Check logs.' }
    }
}
