#!/usr/bin/env groovy


pipeline {
    agent any

    stages {
        stage('printenv') {
            steps {
                sh 'printenv'
            }
        }
    }

    post {
        always {
            deleteDir()
            echo 'done'
        }

        success {
            echo 'success'
        }

        failure {
            echo 'failure'
        }
    }
}
