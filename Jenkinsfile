pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the source code from the version control
                checkout scm
            }
        }

        stage('Run Docker Compose') {
            steps {
                // Run Docker Compose up to start services
                sh 'docker build -t react-app-image .'
            }
        }
    }

    post {
        always {
            // Clean up services by stopping and removing containers
            sh 'docker-compose down'
        }
    }
}
