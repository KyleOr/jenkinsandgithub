pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example: sh 'mvn clean install' for Maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Example: sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis...'
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                // Example: sh 'snyk test'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                // Example: sh 'aws deploy create-deployment --application-name YOUR_APP --deployment-group-name STAGING'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Example: Running automated tests
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                // Example: sh 'aws deploy create-deployment --application-name YOUR_APP --deployment-group-name PRODUCTION'
            }
        }

        stage('Unit and Integration Tests') {
    steps {
        echo 'Running Unit and Integration Tests...'
        // Run your test commands here
    }
    post {
        success {
            emailext subject: "SUCCESS: Test Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "Test stage passed successfully! View logs at: ${env.BUILD_URL}",
                     to: 'developer@example.com'
        }
        failure {
            emailext subject: "FAILURE: Test Stage for ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "Test stage failed. Check logs at: ${env.BUILD_URL}",
                     to: 'developer@example.com',
                     attachmentsPattern: '**/logs/*.*'
        }
    }
}

    }
}
