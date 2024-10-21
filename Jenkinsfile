pipeline {
    agent any
        stage('Deploy to Staging') {
            when {
                branch 'develop'
            }
            steps {
                echo "Deploying to Staging environment..."
                // Add deployment steps for staging (e.g., AWS CLI or Terraform commands)
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to Production environment..."
                // Add deployment steps for production
            }
        }
    post {
        always {
            echo 'Cleaning up...'
            // Cleanup steps (optional)
        }
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
