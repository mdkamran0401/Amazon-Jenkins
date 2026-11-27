
pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {

        stage('Verify Tools') {
            steps {
                bat 'echo Computer Name: %COMPUTERNAME%'
                bat 'echo JAVA_HOME=%JAVA_HOME%'
                bat 'echo MAVEN_HOME=%MAVEN_HOME%'

                bat 'where.exe java'
                bat 'where.exe mvn'
                bat 'where.exe git'

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
