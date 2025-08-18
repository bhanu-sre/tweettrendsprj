pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    stages {
        stage('Git Checkout') {
            steps {
               git branch: 'main', credentialsId: 'GitHUB', url: 'git@github.com:bhanu-sre/tweettrendsprj.git'
            }
        }
    }
}

