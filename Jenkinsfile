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
    stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'cs-sonar-scanner'
    }
    steps{
    withSonarQubeEnv('cs-sonarqube-cloud') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }
}


}
