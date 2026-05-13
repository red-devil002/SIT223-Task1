pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo '=== Stage 1: Build ==='
                echo 'Tool: Maven'
                echo 'Task: Compiling and packaging the application using Maven build automation tool.'
                echo 'Command that would run: mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo '=== Stage 2: Unit and Integration Tests ==='
                echo 'Tools: JUnit (unit tests), TestNG (integration tests)'
                echo 'Task: Running unit tests to verify individual components function correctly.'
                echo 'Task: Running integration tests to ensure components interact as expected.'
                echo 'Commands that would run: mvn test (unit), mvn verify (integration)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo '=== Stage 3: Code Analysis ==='
                echo 'Tool: Checkstyle'
                echo 'Task: Analysing source code for adherence to coding standards and best practices.'
                echo 'Command that would run: mvn checkstyle:check'
            }
        }

        stage('Security Scan') {
            steps {
                echo '=== Stage 4: Security Scan ==='
                echo 'Tool: OWASP Dependency-Check'
                echo 'Task: Scanning all project dependencies for known CVEs and security vulnerabilities.'
                echo 'Command that would run: mvn org.owasp:dependency-check-maven:check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo '=== Stage 5: Deploy to Staging ==='
                echo 'Tool: AWS CLI / SSH'
                echo 'Task: Deploying the packaged application to the AWS EC2 staging instance.'
                echo 'Command that would run: scp target/app.jar ec2-user@staging-server:/apps/'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo '=== Stage 6: Integration Tests on Staging ==='
                echo 'Tool: Selenium / Postman (Newman)'
                echo 'Task: Running end-to-end integration tests against the staging environment.'
                echo 'Task: Verifying the application behaves correctly in a production-like environment.'
                echo 'Command that would run: newman run staging_tests.json --env staging.json'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo '=== Stage 7: Deploy to Production ==='
                echo 'Tool: AWS CLI / SSH'
                echo 'Task: Deploying the validated application to the AWS EC2 production instance.'
                echo 'Command that would run: scp target/app.jar ec2-user@prod-server:/apps/'
            }
        }

    }
}