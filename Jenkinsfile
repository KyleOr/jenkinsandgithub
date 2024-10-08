pipeline {
    agent any
    stages {
        stage('Build') {
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
                    emailext attachLog: true, 
                             body: "Unit and Integration Tests stage passed successfully! View logs at: ${env.BUILD_URL}", 
                             subject: "SUCCESS!: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    emailext attachLog: true, 
                             body: "Unit and Integration Tests stage failed. Check logs at: ${env.BUILD_URL}", 
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
                    emailext attachLog: true, 
                             body: "Security Scan stage passed successfully! View logs at: ${env.BUILD_URL}", 
                             subject: "SUCCESS: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    emailext attachLog: true, 
                             body: "Security Scan stage failed. Check logs at: ${env.BUILD_URL}", 
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
            post {
                always {
                    emailext attachLog: true, 
                             body: "Deploy to Staging completed. View logs at: ${env.BUILD_URL}", 
                             subject: "Deploy to Staging - ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Example command to run tests after staging deployment
            }
            post {
                always {
                    emailext attachLog: true, 
                             body: "Integration Tests on Staging completed. View logs at: ${env.BUILD_URL}", 
                             subject: "Integration Tests on Staging - ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                // Example AWS CLI command to deploy to production
            }
            post {
                always {
                    emailext attachLog: true, 
                             body: "Deployed to Production. View logs at: ${env.BUILD_URL}", 
                             subject: "Deploy to Production - ${env.JOB_NAME} #${env.BUILD_NUMBER}", 
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }
    }
}
