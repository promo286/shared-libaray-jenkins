@Library('shared-lib@main') _

pipeline {
    agent any
    tools {
        maven 'Maven_Home'
    }
    stages {
        stage('Checkout') {
            steps {
                checkoutGitRepo('master', 'https://github.com/promo286/addressbook.git')
            }
        } 

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    runTests()
                    echo 'Tests completed.'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building project...'
                    buildMavenProject()
                    echo 'Build completed.'
                }
            }
        } 
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
