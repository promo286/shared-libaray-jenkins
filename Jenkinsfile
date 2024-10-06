@Library('shared-lib') _

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                  checkoutGitRepo('master', 'https://github.com/promo286/addressbook.git')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    
                    runTests()
                }
            }
        }

        stage('Build') {
            steps {
                script {
                  
                    buildMavenProject()
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
