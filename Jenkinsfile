pipeline {
    agent any
    environment{
        DIRECTORY_PATH='/Users/shreyasaravanan/Desktop/sit223'
        TESTING_ENVIRONMENT='JAVA'
        PRODUCTION_SERVER='AWS EC2'
    }
    stages{
         stage('Delay'){
            steps{
                script{
                    sleep 1
                    //adding a 1 minute delay
                }
            }
        }
        stage('Build'){
            steps{
            echo "fetch the source code from the directory path specified by the environment variable"
            echo "compile the code and generate any neccessary artifacts"
            echo "Build automation tool used- Gradle"
            echo "Build started and completed!" 
            }
        }
        stage('Test'){
            steps{
            echo "running unit tests to ensure the code functions as expected"
            echo "run integration tests to ensure the different components of the application work together as expected"
            echo "running unit tests using JUnit and running integration tests using Selenium"
            echo "Testing started and completed!"    
            }  
        }
        post {
                success {
                    emailext subject: 'Testing successful',
                    body: 'Testing stage passed successfully.',
                    to: 'shreya200564@gmail.com',
                    attachmentsPattern: '**/*.log'
                }
                failure {
                    emailext subject: 'Testing failed',
                    body: 'Testing stage failed.',
                    to: 'shreya200564@gmail.com',
                    attachmentsPattern: '**/*.log'
                }
        }
        stage('Code Analysis'){
            steps{
            echo "analysing code to ensure it meets industry standard"
            echo "Code analysed using SonarQube"
            echo "Code Analysis started and completed!"    
            }
        }
        stage('Security Scan'){
            steps{
            echo "Performing security scan using Code Sonar"
            echo "Security scan completed!"    
            }
        }
        post {
                success {
                    emailext subject: 'Security scan successful',
                    body: 'Security scan stage passed successfully.',
                    to: 'shreya200564@gmail.com',
                    attachmentsPattern: '**/*.log'
                }
                failure {
                    emailext subject: 'Security scan failed',
                    body: 'Security scan stage failed.',
                    to: 'shreya200564@gmail.com',
                    attachmentsPattern: '**/*.log'
                }
        }
        stage('Deploy to Staging'){
            steps{
            echo "deploy the application to a staging server AWS EC2"
            echo "Deployment started and completed!"    
            }
        }
        stage('Integration tests'){
            steps{
            echo "running integration tests on the staging environment to ensure the application functions as expected in a production-like environment" 
            echo "integration tests on staging completed!"  
            }
        }
        stage('Deploy to Production'){
            steps{
            echo "Deploying code to the production server: ${PRODUCTION_ENVIRONMENT}"
            echo "Deployment to Production started and completed!"    
            }
        }
    }
}

