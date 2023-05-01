pipeline {
    agent any
    tools {
        maven 'MAVEN_4_0_0'
        jdk 'JDK17'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test -Dtest="**/unitTests/*.java"'
                junit 'target/surefire-reports/**/*.xml'
            }
        }
    }
}