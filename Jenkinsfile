pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                branch 'main' // Only run on the main branch
            }
            steps {
                sh 'echo "Building on main branch"'
            }
        }
        stage('Deploy to Staging') {
            when {
                allOf {
                    branch 'develop'
                    environment name: 'DEPLOY_TO_STAGING', value: 'true'
                }
            }
            steps {
                sh 'echo "Deploying to staging"'
            }
        }
        stage('Run Tests if not main') {
            when {
                not { branch 'main' }
            }
            steps {
              sh 'echo "Running tests on non-main branch"'
            }
        }
        stage('Deploy to Production only on tags') {
            when {
                tag "v*" // Runs only on tags starting with 'v'
            }
            steps {
                sh 'echo "Deploying to production"'
            }
        }
    }
}
