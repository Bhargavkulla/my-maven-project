@Library('maven-shared-library') _ // Load your shared library

pipeline {
    agent any

    tools {
        maven 'Maven 3.6.3'  // Replace with the name of your Maven installation in Jenkins
    }

    environment {
        MAVEN_HOME = tool name: 'Maven 3.6.3', type: 'Maven'
        JAVA_HOME = tool name: 'JDK 11', type: 'JDK'  // Set the correct JDK version
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm  // Checkout the code from your repository
            }
        }

        stage('Build') {
            steps {
                script {
                    // Call the shared library function to build the Maven project
                    mavenBuild()
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // You can add additional testing steps here, e.g., running unit tests
                    echo 'Running tests...'
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy to your environment (if needed)
                    echo 'Deploying project...'
                    sh 'mvn deploy'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}
