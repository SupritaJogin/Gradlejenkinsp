pipeline {
    agent any

    tools {
        gradle 'Gradle'  // Ensure 'Gradle' matches the name configured in Jenkins global tool settings
        jdk 'JDK'        // Ensure 'JDK' matches your configured JDK name
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/Gradlejenkinsp.git'
            }
        }
        stage('Build') {
            steps {
                bat 'gradle clean build'
            }
        }
        stage('Test') {
            steps {
                bat 'gradle test'
            }
        }
        stage('Package') {
            steps {
                bat 'gradle assemble'
            }
        }
    }

    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}

      
