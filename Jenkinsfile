pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests'
            }
            post {
                success {
                     mail body: 'Unit and Integration Tests completed SUCCESSFULLY.', subject: 'Unit and Integration Tests Status', to: 'meghatri05@gmail.com', attachlog: true
                }
                failure {
                    success {
                     mail body: 'Failure! Please check logs.', subject: 'Unit and Integration Tests Status', to: 'meghatri05@gmail.com'
                }
                    
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing a security'
            }
            post {
                always {
                    emailext (
                        subject: 'Security Scan Status',
                        to: 'meghatri05@gmail.com',
                        body: "Security Scan completed SUCCESSFULLY.",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        subject: 'Security Scan Status',
                        to: 'meghatri05@gmail.com',
                        body: 'Failure! Please check the logs.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment'
            }
            post {
                always {
                    emailext (
                        subject: 'Integration Tests on Staging Status',
                        to: 'meghatri05@gmail.com',
                        body: "Integration Tests on Staging completed SUCCESSFULLY.",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        subject: 'Integration Tests on Staging Status',
                        to: 'meghatri05@gmail.com',
                        body: 'Failure! Please check the logs.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application'
            }
            post {
                always {
                    emailext (
                        subject: 'Deploying to Production',
                        to: 'meghatri05@gmail.com',
                        body: "Deployment completed SUCCESSFULLY.",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        subject: 'Deploying to Production',
                        to: 'meghatri05@gmail.com',
                        body: 'Failure! Please check the logs',
                        attachLog: true
                    )
                }
            }
        }
    }
}
