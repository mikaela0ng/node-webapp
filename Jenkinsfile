pipeline {
    agent { label 'linux-node' }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'b7022718-432e-45cb-8269-ad9dd65959ff', branch: 'main', url: 'https://github.com/mikaela0ng/node-webapp.git'
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

