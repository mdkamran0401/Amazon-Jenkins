
pipeline {
    agent {
        label 'Node1'
    }

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                sh '''#!/bin/bash
                echo "Building branch: $BRANCH_NAME"
                mvn compile
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''#!/bin/bash
                mvn clean install
                '''
            }
        }

        stage('PR Information') {
            when {
                changeRequest()
            }
            steps {
                echo "This is a Pull Request build"
                echo "PR ID: ${env.CHANGE_ID}"
                echo "Target branch: ${env.CHANGE_TARGET}"
            }
        }
    }

    post {
        success {
            emailext(
                to: 'kamran.abc.reports@gmail.com',
                subject: "Multibranch Pipeline - ${env.JOB_NAME} - SUCCESS",
                body: "Pipeline successful. Branch: ${env.BRANCH_NAME}"
            )
        }

        failure {
            emailext(
                to: 'kamran.abc.reports@gmail.com',
                subject: "Multibranch Pipeline - ${env.JOB_NAME} - FAILURE",
                body: "Pipeline failed. Branch: ${env.BRANCH_NAME}"
            )
        }
    }
}
