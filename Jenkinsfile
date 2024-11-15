pipeline {
    agent any
    tools{
        nodejs 'Node_16'
    }
    stages {
        stage("Checkout the code"){
            steps{
                git url: 'https://github.com/VelinaGesh/StugentRegistryApp'
            }
            
        }
        stage("Set up Node.js"){
            steps{
                sh 'node -v'
                sh 'npm -v'
            }
        }
        stage("Install Dependencies"){
            steps{
                sh 'npm install'
            }
        }
        stage("Start application"){
            steps{
                sh 'npm start &'
            }
        }
        stage("Test"){
            steps{
               sh 'npm test'
            }
        }
    }
    post{
        always{
            echo 'Pipeline finished. Cleanup if necessary.'
        }
        success{
            echo 'Pipeline completed successfully!'
        }
        failure{
            echo 'Pipeline failed. Check the logs for more details.'
        }
    }
}
