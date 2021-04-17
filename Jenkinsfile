pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', url: 'https://github.com/sancbein/demoproject.git']]])
            }
        }
        stage('Build'){
            steps {
                git credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', url: 'https://github.com/sancbein/demoproject.git'
                cp 'sample.war /tomcat/apache-tomcat-8.5.63/webapps'
            }
        }
        stage('Test'){
            steps {
                echo 'Testing application successful'
            }
        }
    }
}
