pipeline {
    agent any
    tools {
        gradle 'GRADLE'  // ensure this matches Jenkins Tool config
        jdk 'JAVA'       // ensure this matches Jenkins Tool config
    }
    stages {
        stage('Build') {
            steps {
                bat 'gradlew.bat clean build'
            }
        }
        stage('Test') {
            steps {
                bat 'gradlew.bat test'
            }
        }
    }
}
