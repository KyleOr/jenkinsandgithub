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
                    // Email notification with build log and attachments for Unit and Integration Tests
                    emailext attachLog: true, 
                             attachmentsPattern: '**/builds/${env.BUILD_NUMBER}/log',
                             body: "${currentBuild.currentResult}: Unit and Integration Tests stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}", 
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             to: 'kyleerikoris@gmail.com'
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
                    // Email notification with build log and summary for Code Analysis
                    emailext attachLog: true,
                             body: "${currentBuild.currentResult}: Code Analysis stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}",
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Code Analysis Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             to: 'kyleerikoris@gmail.com'
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
                    // Email notification with build log and summary for Security Scan
                    emailext attachLog: true,
                             body: "${currentBuild.currentResult}: Security Scan stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}",
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
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
                    // Email notification for Deploy to Staging
                    emailext attachLog: true,
                             body: "${currentBuild.currentResult}: Deploy to Staging for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}",
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Deploy to Staging for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
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
                    // Email notification for Integration Tests on Staging
                    emailext attachLog: true,
                             body: "${currentBuild.currentResult}: Integration Tests on Staging for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}",
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Integration Tests on Staging for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
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
                    // Email notification for Deploy to Production
                    emailext attachLog: true,
                             body: "${currentBuild.currentResult}: Deploy to Production for ${env.JOB_NAME} #${env.BUILD_NUMBER}\nMore info at: ${env.BUILD_URL}",
                             recipientProviders: [developers(), requestor()],
                             subject: "Jenkins Build ${currentBuild.currentResult}: Deploy to Production for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             to: 'kyleerikoris@gmail.com'
                }
            }
        }
    }
}
