pipeline {
    agent { label 'linux-node' }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'mikaela0ng', url: 'https://github.com/mikaela0ng/node-webapp.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-webapp .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name node-webapp-container node-webapp'
            }
        }
    }
}

