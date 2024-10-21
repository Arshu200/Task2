pipeline {
    agent any
    stages { // All stages must be enclosed within 'stages'
        stage('Build') {
            steps {
                echo "Building the project..."
                // Add build steps here (e.g., compile, test)
            }
        }
        stage('Deploy to Staging') {
            when {
                branch 'dev'  // Use 'dev' for your development branch
            }
            steps {
                echo "Deploying to Staging environment..."
                // Add deployment steps for staging
                sh '''
                    echo "Printing the contents of file1.txt:"
                    cat file1.txt
                '''
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to Production environment..."
                // Add deployment steps for production
                sh '''
                    echo "Printing the contents of file1.txt:"
                    cat file1.txt
                '''
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            // Add any necessary cleanup steps here
        }
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}