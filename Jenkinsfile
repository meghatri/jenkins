pipeline {
    agent any
    environment {
        DIRECTORY_PATH = 'C:/Users/MeghaKhatri/Megha/Deakin/2023_T2/Deakin-Unit-Page-main/index.html' // Update with your actual code directory path
        TESTING_ENVIRONMENT = 'S222480654_MeghaK-DEV'
        PRODUCTION_ENVIRONMENT = 'MeghaKhatri-PROD'
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path: ${DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application to the testing environment: ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment: ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
