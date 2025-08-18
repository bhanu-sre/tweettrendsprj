pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = "/opt/apache-maven-4.0.0-rc-4/bin:$PATH"
}    
    stages {
        stage('Git Checkout') {
            steps {
               git branch: 'main', credentialsId: 'GitHUB', url: 'https://github.com/bhanu-sre/tweettrendsprj.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean install -DskipTests'
        }
    }
}
}
