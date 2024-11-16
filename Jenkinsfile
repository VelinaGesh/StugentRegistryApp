pipeline {
    agent any
    tools {
        nodejs 'Node_16' // Make sure Node_16 is configured in Jenkins under Global Tool Configuration
    }
    stages {
        stage("Checkout the code") {
            steps {
                git url: 'https://github.com/VelinaGesh/StugentRegistryApp'
            }
        }
        stage("Set up Node.js") {
            steps {
                bat 'node -v'   // Checks Node.js version
                bat 'npm -v'    // Checks npm version
            }
        }
        stage("Install Dependencies") {
            steps {
                bat 'npm install'  // Installs all the dependencies
            }
        }
        stage("Start application") {
            steps {
                bat 'start npm start' // Starts the application in the background
            }
        }
        stage("Test") {
            steps {
                // You can add any test commands here
                echo 'Tests not implemented yet.'
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished. Cleanup if necessary.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for more details.'
        }
    }
}
