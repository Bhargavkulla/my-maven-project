@Library('maven-lib@main') _

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                mavenBuild('clean package')
            }
        }
    }
}
