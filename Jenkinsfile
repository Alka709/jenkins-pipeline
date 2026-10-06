pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Alka709/jenkins-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting automated build...'
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
