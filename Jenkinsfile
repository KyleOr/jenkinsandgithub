pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example using Maven to build the project
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Example using Maven to run tests
                sh 'mvn test'
            }
            post {
                success {
                    emailext subject: "SUCCESS: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             body: "Unit and Integration Tests stage passed successfully! View logs at: ${env.BUILD_URL}",
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    emailext subject: "FAILURE: Unit and Integration Tests Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             body: "Unit and Integration Tests stage failed. Check logs at: ${env.BUILD_URL}",
                             to: 'kyleerikoris@gmail.com',
                             attachmentsPattern: '**/logs/*.*'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis...'
                // Example using SonarQube scanner for static code analysis
                sh 'sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.host.url=http://your-sonarqube-url -Dsonar.login=your_token'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                // Example using Snyk to scan for security vulnerabilities
                sh 'snyk test'
            }
            post {
                success {
                    emailext subject: "SUCCESS: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             body: "Security Scan stage passed successfully! View logs at: ${env.BUILD_URL}",
                             to: 'kyleerikoris@gmail.com'
                }
                failure {
                    emailext subject: "FAILURE: Security Scan Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                             body: "Security Scan stage failed. Check logs at: ${env.BUILD_URL}",
                             to: 'kyleerikoris@gmail.com',
                             attachmentsPattern: '**/logs/*.*'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                // Example AWS CLI command to deploy to an EC2 instanc
                sh 'aws deploy create-deployment --application-name YOUR_APP --deployment-group-name STAGING --s3-location bucket=your-bucket,bundleType=zip,key=your-app.zip'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Example command to run tests after staging deployment
                sh './run-integration-tests.sh'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                // Example AWS CLI command to deploy to production
                sh 'aws deploy create-deployment --application-name YOUR_APP --deployment-group-name PRODUCTION --s3-location bucket=your-bucket,bundleType=zip,key=your-app.zip'
            }
        }
    }
}
