pipeline {
    agent {
        label 'agent-1'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                // Add your build steps here
                echo 'Build complete.'
            }
        }
        stage('Test') {
            steps {
                echo 'Starting the Test stage...'
                // Add your test steps here
                echo 'Testing complete.'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting the Deploy stage...'
                // Add your deployment steps here
                echo 'Deployment complete.'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
