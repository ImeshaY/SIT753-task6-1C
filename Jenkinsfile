pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'        
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Build Status: SUCCESS",
                         body: "The Build stage completed successfully."
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Test Status: SUCCESS",
                         body: "The Test stage completed successfully."
                }
            }
        }
    }
}
