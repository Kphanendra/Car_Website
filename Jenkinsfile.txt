pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Kphanendra/Car_Website.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                echo "Building Application"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/carwebsite/*
                sudo cp -r * /var/www/html/carwebsite/
                '''
            }
        }
    }
}
