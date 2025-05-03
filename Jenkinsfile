library identifier: 'maven-lib@main', retriever: modernSCM([
  $class: 'GitSCMSource',
  remote: 'https://github.com/Bhargavkulla/jenkins-shared-lib.git'
])

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
