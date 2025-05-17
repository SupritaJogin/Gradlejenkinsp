pipeline {
    agent any

    tools {
        gradle 'Gradle'  // make sure this matches your Jenkins config
        jdk 'JDK'        // make sure this matches your Jenkins config
    }

    stages {             // <----- stages block is mandatory
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/Gradlejenkinsp.git'
            }
        }
        stage('Build') {
            steps {
                bat 'gradle clean install'  // fix typo: 'gardle' → 'gradle'
            }
        }
        stage('Test') {
            steps {
                bat 'gradle test'
            }
        }
        stage('Package') {
            steps {
                bat 'gradle package'
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

       
