pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'demo-Rel2',
                    credentialsId: 'GithubAppCred',
                    url: 'https://github.com/mdkamran0401/Amazon-Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }
}
