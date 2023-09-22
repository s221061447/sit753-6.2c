pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = "D:\\Deakin\\Trimester 5\\SIT753\\Week6\\Code"
        TESTING_ENVIRONMENT = "Test"
        PRODUCTION_ENVIRONMENT = "Prod"
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Stage 1: Building the code using Maven or another build automation tool."
                // sh "mvn clean install" // Example Maven command
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Stage 2: Running unit tests and integration tests."
                // sh "npm test" // Example test command
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Stage 3: Performing code analysis using SonarQube, a code analysis tool."
                // sh "sonar-scanner" // Example SonarQube command
            }
        }
        stage('Security Scan') {
            steps {
                echo "Stage 4: Performing a security scan using a security scanning tool (e.g., OWASP ZAP)."
                // sh "owasp-zap -cmd" // Example OWASP ZAP command
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Stage 5: Deploying the application to the staging server (e.g., AWS EC2 instance)."
                // sh "aws s3 cp ./target/app.jar s3://staging-bucket" // Example AWS deployment command
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Stage 6: Running integration tests on the staging environment."
                // sh "curl http://staging-server:8080/health-check" // Example integration test command
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Stage 7: Deploying the application to the production server (e.g., AWS EC2 instance)."
                // sh "aws s3 cp ./target/app.jar s3://production-bucket" // Example AWS deployment command
            }
        }
    }

    post {
        always {
            emailext to: "techpauljose@gmail.com",
            subject: "Jenkins Build Log",
            body: "Jenkins",
            attachLog: true
        }
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline execution failed!"
        }
    }
}