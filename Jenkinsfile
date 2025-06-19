pipeline {
    agent any

    environment {
        // Common environment variables
        APP_NAME = 'MyApp'
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out branch: ${env.BRANCH_NAME}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
                // Replace with your actual build command
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests on branch: ${env.BRANCH_NAME}"
                // Replace with your test command
                sh './gradlew test'
            }
        }

        stage('Deploy') {
            when {
                // Only deploy from main and develop branches
                anyOf {
                    branch 'main'
                    branch 'develop'
                }
            }
            
