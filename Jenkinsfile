pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('GIT') {
            steps {
                echo 'Getting project from github'
                checkout scm
            }
        }

        stage('CLEAN') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('COMPILE') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('SONARQUBE') {
            steps {
                sh 'mvn sonar:sonar'
            }
        }        
    }
}

