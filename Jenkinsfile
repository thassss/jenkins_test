pipeline {
    agent any

    environment {
        DEPLOY_ENV = 'production'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Deploy to Production') {
            when {
                environment name: 'DEPLOY_ENV', value: 'production'
            }
            steps {
                echo 'Deploying to production...'
            }
        }

        stage('Deploy to Staging') {
            when {
                environment name: 'DEPLOY_ENV', value: 'staging'
            }
            steps {
                echo 'Deploying to staging...'
            }
        }
    }
}

