pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/argiebee/my-app.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                  sh 'mvn clean install'
            }
        }
    }
    post {
        always {
            junit '**/target/reports/**/*.xml'
        }
    }
}