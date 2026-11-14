pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly test and test
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm git ') {
            steps {
                git branch: 'IB-Demo_PR', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('compile ') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }

        
    }

post {
        success {
            emailext(
                to: 'kamran.abc.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - SUCCESS",
                body: "Pipeline completed successfully. Build URL: ${env.BUILD_URL}"
)
  }
    
        failure {
            emailext(
                to: 'kamran.abc.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - FAILURE",
                body: "Pipeline failed. Please check the console output: ${env.BUILD_URL}"
)
   }

  }


}
