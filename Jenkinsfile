pipeline {
    agent any
    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }{
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/Gradlejenkinsp.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Package') {
            steps {
                bat 'mvn package'
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
