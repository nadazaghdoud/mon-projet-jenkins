pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
              
                git branch: 'main', url: 'https://github.com/nadazaghdoud/mon-projet-jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('MVN SONARQUBE') {
            steps {
                // Exécuter l'analyse SonarQube
                withSonarQubeEnv('SonarQubeServer') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}

