pipeline {
    agent any
    tools {
        maven 'MAVEN_3_6_3'
        jdk 'JDK_17'
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