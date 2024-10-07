pipeline {
    agent any
    stages {
        stage('Test Email') {
            steps {
                emailext attachLog: true, 
                         body: 'This is a test email sent from Jenkins.', 
                         subject: 'Test Email from Jenkins', 
                         to: 'kyleerikoris@gmail.com'
            }
        }
    }
}
