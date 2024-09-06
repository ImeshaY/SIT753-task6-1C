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
    }
}
