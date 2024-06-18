pipeline {
    agent any
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
}
