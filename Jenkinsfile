pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo 'Task: Compile and package the code.'
                echo 'Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Tests...'
                echo 'Task: Run unit tests to ensure code correctness and integration tests for component integration.'
                echo 'Tool: JUnit for unit tests, TestNG for integration tests'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing Code...'
                echo 'Task: Analyze the code to ensure it meets industry standards.'
                echo 'Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for Vulnerabilities...'
                echo 'Task: Perform a security scan on the code to identify vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
            post {
                success {
                    emailext (
                        body: "The Unit and Integration Tests stage has successfully completed.", 
                        subject: "Pipeline Success: Security Scan - ${env.JOB_NAME} [${env.BUILD_NUMBER}]", 
                        to: 'liambishop54322@gmail.com',
                        attachLog: true
                    )
                }
                failure {
                    mail to: 'liambishop54322@gmail.com',
                    subject: "Pipeline Failure: Security Scan - ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                    body: "The Security Scan stage failed. Please review the logs."
                         //attachmentsPattern: 'logs/*.log'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                echo 'Task: Deploy the application to a staging server.'
                echo 'Tool: Ansible or AWS CLI'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                echo 'Task: Run integration tests on the staging environment.'
                echo 'Tool: Selenium for UI testing or Postman for API testing'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                echo 'Task: Deploy the application to a production server.'
                echo 'Tool: Ansible or AWS CLI'
            }
        }
    }
}

