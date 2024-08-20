pipeline{
    agent any
    environment {
        DIRECTORY_PATH = '/var/jenkins_home/workspace/5.1P_Pipeline'
        TESTING_ENVIRONMENT = 'Testing_Env'
        PRODUCTION_ENVIRONMENT = 'LiamBishop_Prod'
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts."
            }
        }

        stage('Test') {
            steps {
                echo "Unit tests."
                echo "Integration tests."
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep 10
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment specified by the environment variable: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
                stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment specified by the environment variable: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
