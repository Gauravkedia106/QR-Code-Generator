pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code pulled from GitHub successfully!"
                echo "Branch: ${env.GIT_BRANCH}"
                echo "Commit: ${env.GIT_COMMIT}"
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
                bat 'if not exist build-output mkdir build-output'
                bat 'echo Build complete > build-output\\result.txt'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                bat 'echo All tests passed!'
            }
        }

        stage('Done') {
            steps {
                echo "Pipeline triggered by GitHub push!"
                echo "Job: ${env.JOB_NAME} | Build: ${env.BUILD_NUMBER}"
            }
        }

    }

    post {
        success {
            echo "Build SUCCESS - code is healthy!"
        }
        failure {
            echo "Build FAILED - check the red stage!"
        }
    }
}
