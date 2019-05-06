#!/usr/bin/env groovy

pipeline {
    agent {
        docker { image 'centos/python-36-centos7:1' }
    }

    stages {
        stage('printenv') {
            steps {
                sh 'printenv'
                sh 'python --version'
            }
        }

        stage('minimal test') {
            steps {
                echo 'minimal test'
            }
        }

        stage('full test') {
            when { anyOf { branch 'master'; branch 'PR-*' } }
            steps {
                echo 'full test'
            }
        }

        stage('deploy') {
            when { tag '*' }
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        always {
            echo 'done...'
        }
        success {
            echo 'success'
        }
        failure {
            echo 'failure'
        }
    }
}
