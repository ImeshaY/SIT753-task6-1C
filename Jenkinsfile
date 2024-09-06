pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                sh 'mvn clean package'  // Using Maven to build
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Build Status: SUCCESS",
                         body: "The Build stage completed successfully."
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                sh 'mvn test'  // Running tests with Maven
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Unit and Integration Tests Status: SUCCESS",
                         body: "Unit and Integration Tests completed successfully."
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...'
                sh 'mvn sonar:sonar'  // Using SonarQube for code analysis
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Code Analysis Status: SUCCESS",
                         body: "Code Analysis completed successfully."
                }
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                sh 'mvn dependency-check:check'  // Using OWASP Dependency-Check for security scanning
            }
            post {
                success {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Security Scan Status: SUCCESS",
                         body: "Security Scan completed successfully."
                }
                failure {
                    mail to: 'imesha.ilangasinghe@gmail.com',
                         subject: "Security Scan Status: FAILURE",
                         body: "Security Scan failed. Please check the logs.",
                         attachLog: true
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Add deployment steps here, e.g., using SSH to deploy to an EC2 instance
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Run integration tests in staging environment
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Add production deployment steps here, e.g., using SSH to deploy to an EC2 instance
            }
        }
    }
}
