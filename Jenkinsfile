pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Execute Batch Script') {
            steps {
                script {
                    // Print current directory to confirm workspace
                    echo "Current directory is:"
                    bat 'echo %cd%'

                    // List files in the current directory
                    echo "Listing files in the current directory:"
                    bat 'dir'

                    // Execute the batch script
                    echo "Executing list_file.sh script:"
                    def result = bat(script: 'list_file.sh', returnStdout: true).trim()

                    // Print the output to the Jenkins console
                    echo "The result of the script is: \n${result}"
                }
            }
        }
    }
}
