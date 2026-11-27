
pipeline {
    agent {
        label 'kam-WinNode1'
    }

    stages {
        stage('Build') {
            steps {
                bat '"C:\\Tools\\apache-maven-3.10.2\\bin\\mvn.cmd" clean install'
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
