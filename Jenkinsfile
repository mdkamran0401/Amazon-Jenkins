
pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {
        stage('Verify Tools') {
            steps {
                bat '''
                echo Computer Name: %COMPUTERNAME%
                echo JAVA_HOME=%JAVA_HOME%
                echo MAVEN_HOME=%MAVEN_HOME%

                C:\\Windows\\System32\\where.exe java || echo Java not found on PATH

                "%JAVA_HOME%\\bin\\java.exe" -version || echo Java check failed

                "C:\\Tools\\apache-maven-3.10.2\\bin\\mvn.cmd" -version || echo Maven check failed

                "C:\\Program Files\\Git\\cmd\\git.exe" --version || echo Git check failed
                '''
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
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed. Check the console output.'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
