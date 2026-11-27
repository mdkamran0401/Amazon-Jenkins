
pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {

        stage('Verify Tools') {
            steps {
                bat 'echo Computer Name: %COMPUTERNAME%'
                bat 'java -version'
                bat 'mvn -version'
                bat 'git --version'
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
