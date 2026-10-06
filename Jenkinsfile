pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

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
                sh '''
                    mkdir -p deployed
                    cp app.sh deployed/
                    echo "Application deployed successfully!"
                '''
            }
        }
    }

    post {
        success {
            echo 'POST-BUILD: Deployment completed successfully!'
        }

        failure {
            echo 'POST-BUILD: Deployment failed!'
        }

        always {
            echo 'POST-BUILD: Pipeline execution completed.'
        }
    }
}
