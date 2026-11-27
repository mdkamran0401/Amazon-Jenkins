
pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {

        stage('Verify Tools') {
            steps {
                bat 'hostname'
                bat 'java -version'
                bat 'mvn -version'
                bat 'git --version'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'demo-Rel2',
                    url: 'https://github.com/mdkamran0401/Amazon-Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully on Windows Agent!'
        }

        failure {
            echo 'Build failed. Please check the console output.'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
