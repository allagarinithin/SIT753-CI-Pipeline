pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:${env.PATH}"
    }

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Compile the source code and package it into a deployable artefact.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Run unit tests to verify individual components, then integration tests to verify components work together.'
                echo 'Tools: JUnit for unit tests, Selenium WebDriver for integration tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Analyse the source code against industry coding standards to detect code smells, duplication and maintainability issues.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scan the application and its dependencies for known vulnerabilities and CVEs.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Task: Deploy the packaged artefact to the staging server for pre-production verification.'
                echo 'Tool: AWS CLI deploying to an AWS EC2 instance'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Task: Run the integration test suite against the staging environment to confirm the application behaves correctly in a production-like setting.'
                echo 'Tools: Postman with Newman CLI'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Task: Promote the verified build to the production server and make it live to end users.'
                echo 'Tool: AWS CodeDeploy to an AWS EC2 instance'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully - all seven stages passed.'
        }
        failure {
            echo 'Pipeline failed. Please review the console output above.'
        }
    }
}
