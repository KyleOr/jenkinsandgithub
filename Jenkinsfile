pipeline {
    agent any
    stages {
        stage('Build!') {
            steps {
                echo 'Building the code...'
                // Example using Maven to build the project
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Example using Maven to run tests
            }
            post {
                success {
                    // Corrected log attachment with Ant GLOB pattern
                    emailext attachmentsPattern: '**/builds/${env.BUILD_NUMBER}/log',
                             body: "Unit and Integration Tests stage passed successfully! See the attached logs or view them at: ${env.BUILD_URL}", 
                             subject: "SUCCESS: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    // Corrected log attachment with Ant GLOB pattern
                    emailext attachmentsPattern: '**/builds/${env.BUILD_NUMBER}/log',
                             body: "Unit and Integration Tests stage failed. See the attached logs or view them at: ${env.BUILD_URL}", 
                             subject: "FAILURE: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis...'
                // Example using SonarQube scanner for static code analysis
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                // Example using Snyk to scan for security vulnerabilities
            }
            post {
                success {
                    emailext body: "Security Scan stage passed successfully! View logs at: ${env.BUILD_URL}", 
                             subject: "SUCCESS: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    emailext body: "Security Scan stage failed. Check logs at: ${env.BUILD_URL}", 
                             subject: "FAILURE: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                // Example AWS CLI command to deploy to an EC2 instance
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Example command to run tests after staging deployment
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                // Example AWS CLI command to deploy to production
            }
        }
    }
}
