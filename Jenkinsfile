
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "🔄 Checking out branch: ${env.BRANCH_NAME}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "⚙️ Building project from branch: ${env.BRANCH_NAME}"
                bat 'echo Simulating build...'
            }
        }

        stage('Test') {
            steps {
                echo "🧪 Running tests on branch: ${env.BRANCH_NAME}"
                bat 'echo Running tests...'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'   // Deploy only if current branch is 'main'
            }
            steps {
                echo "🚀 Deploying application from main branch"
                bat 'echo Deploying build...'
            }
        }
    }

    post {
        always {
            echo "✅ Pipeline completed for branch: ${env.BRANCH_NAME}"
        }
    }
}
