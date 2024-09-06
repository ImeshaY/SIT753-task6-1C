pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Task performed: Build the code using a build automation tool to compile and package the code'
                echo 'Tool: Maven'        
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task performed: Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected'
                echo 'Tool: TestNG'
            }
            post {
                success {
                    mail(
                        to: 'imesha.ilangasinghe@gmail.com',
                        subject: "Unit and Integration Test Status: SUCCESS",
                        body: "The Unit and Integration Test stage completed successfully.",
                        attachLog: true
                    )
                }
                failure {
                    mail(
                        to: 'imesha.ilangasinghe@gmail.com',
                        subject: "Unit and Integration Test Status: FAILURE",
                        body: "The Unit and Integration Test stage failed. Please check the attached logs for details.",
                        attachLog: true
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task performed: Integrate a code analysis tool to analyse the code and ensure it meets industry standards'
                echo 'Tool: SonarQube'  
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task performed: Perform a security scan on the code using a tool to identify any vulnerabilities'
                echo 'Tool: OWASP Dependency-Check'  
            }
            post {
                success {
                    emailext(
                        to: 'imesha.ilangasinghe@gmail.com',
                        subject: "Security Scan Status: SUCCESS",
                        body: "The Security Scan stage completed successfully.",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'imesha.ilangasinghe@gmail.com',
                        subject: "Security Scan Status: FAILURE",
                        body: "The Security Scan stage failed. Please check the attached logs for details.",
                        attachLog: true
                    )
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task performed: Deploy the application to a staging server ('
                echo 'Tool: AWS EC2 instance'  
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task performed: Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment.'
                echo 'Tool: Selenium'  
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task performed: Deploy the application to a production server '
                echo 'Tool: AWS EC2 instance'  
            }
        }
        
    }
}
