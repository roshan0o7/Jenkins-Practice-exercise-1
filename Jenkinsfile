pipeline {
    agent any
environment {
        SLACK_CHANNEL = '#general'  // or use '@roshan-sax1539' for direct message
        SLACK_CREDENTIAL_ID = 'slackToken-v4' // The ID you used in the Jenkins configuration
    }
stages {
    stage('Run Script') {
            steps {
                script {
                    // Ensure the script is executable
                    sh 'chmod +x bash.sh'
                    // Run the script
                    sh './bash.sh'
                }
            }
        }
    }
post {
        success {
            slackSend (
                channel: env.SLACK_CHANNEL,
                color: 'good',
                message: "Build Successful: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                teamDomain: 'roshan-sax1539.slack.com',
                tokenCredentialId: env.SLACK_CREDENTIAL_ID
            )
        }
        failure {
            slackSend (
                channel: env.SLACK_CHANNEL,
                color: 'danger',
                message: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                teamDomain: 'roshan-sax1539.slack.com',
                tokenCredentialId: env.SLACK_CREDENTIAL_ID
            )
        }
    }
}
