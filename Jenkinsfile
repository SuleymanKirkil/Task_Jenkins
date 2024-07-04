pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Simulate a build step
                    echo 'Building...'
                    sh 'echo "Hello, My Beautiful World. Son!"'
                }
            }
        }
    }

    post {
        always {
            script {
                // Send an email notification
                emailext (
                    to: 'suleyman@clarusway.com', // Replace with your email address
                    subject: "Jenkins Build - ${currentBuild.fullDisplayName}",
                    body: """
                    Build Status: ${currentBuild.currentResult}
                    Project Name: ${env.JOB_NAME}
                    Build Number: ${env.BUILD_NUMBER}
                    Build URL: ${env.BUILD_URL}
                    """,
                    attachLog: true
                )
            }
        }
    }
}
