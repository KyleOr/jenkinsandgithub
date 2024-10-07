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
                always {
                    // Email with attached log for Unit and Integration Tests
                    emailext attachLog: true, 
                             body: 'Unit and Integration Tests completed. Check logs for details.', 
                             subject: 'Unit and Integration Tests - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis...'
                // Example using SonarQube scanner for static code analysis
            }
            post {
                always {
                    // Email with attached log for Code Analysis
                    emailext attachLog: true, 
                             body: 'Code Analysis completed. Check logs for details.', 
                             subject: 'Code Analysis - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
                }
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                // Example using Snyk to scan for security vulnerabilities
            }
            post {
                always {
                    // Email with attached log for Security Scan
                    emailext attachLog: true, 
                             body: 'Security Scan completed. Check logs for details.', 
                             subject: 'Security Scan - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
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
                    // Email with attached log for Deploy to Staging
                    emailext attachLog: true, 
                             body: 'Deployed to Staging. Check logs for details.', 
                             subject: 'Deploy to Staging - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
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
                    // Email with attached log for Integration Tests on Staging
                    emailext attachLog: true, 
                             body: 'Integration Tests on Staging completed. Check logs for details.', 
                             subject: 'Integration Tests on Staging - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
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
                    // Email with attached log for Deploy to Production
                    emailext attachLog: true, 
                             body: 'Deployed to Production. Check logs for details.', 
                             subject: 'Deploy to Production - Build ${env.BUILD_NUMBER}', 
                             to: 's223399201@deakin.edu.au'
                }
            }
        }
    }
}
