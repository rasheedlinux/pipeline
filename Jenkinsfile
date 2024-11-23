pipeline {
    agent {
        label 'agent-1'
    }
parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                // Add your build steps here
                echo 'Build complete.'
            }
        }
        stage('Example1') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
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
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
            deleteDir()
        }
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
