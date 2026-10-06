pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'chmod +x app.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
                sh './app.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                echo 'Application deployed successfully!'
            }
        }
    }
}
