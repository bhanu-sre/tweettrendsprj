pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    stages {
        stage('Git Checkout') {
            steps {
               git branch: 'main', credentialsId: 'GitHUB', url: 'https://github.com/bhanu-sre/tweet-trend-1.git'
            }
        }
    }
}

