pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK17'
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Eleaguvictoria/NUMBERGUESSGAME.git'
            }
        }

        stage('Build Application') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp target/*.war /var/lib/tomcat9/webapps/'
            }
        }

    }

    post {
        success {
            echo 'Build and Deployment Successful!'
        }

        failure {
            echo 'Pipeline Failed. Check logs.'
        }
    }
}
