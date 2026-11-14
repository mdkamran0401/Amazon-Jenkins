pipeline {
    agent { label 'Node1' }

    stages {

        stage('pull scm git ') {
            steps {
                git branch: 'main', url: 'https://github.com/mdkamran0401/Amazon-Jenkins.git'
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
            body: "Your Jenkins Pipeline is successful"
        )
    }

    failure {
        emailext(
            to: 'kamran.abc.reports@gmail.com',
            subject: "Jenkins Pipeline - ${env.JOB_NAME} - FAILURE",
            body: "Your Jenkins Pipeline has failed"
        )
    }
    
   }

}
