pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Use the 'tool' directive to specify the Maven installation
                tool 'Maven'
                // Execute Maven build commands
                sh 'mvn clean package'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests'
                // Example: JUnit or TestNG for unit tests
                // sh 'mvn test'
                
                echo 'Running integration tests'
                // Example: Selenium for integration tests
                // sh 'mvn verify'
            }
            post {
                success {
                    emailext body: Unit and Integration Tests passed successfully
                    subject: 'Unit and Integration Tests Passed',
                    mail to: 'kniveditha30@gmail.com',
                    attachLog: true
                }
                failure {
                    emailext body: Unit and Integration Tests failed                
                    subject: 'Unit and Integration Tests Failed',
                    mail to: 'kniveditha30@gmail.com',
                    attachLog: true
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis using SonarQube'
                // Example: SonarQube for code analysis
                // sh 'sonar-scanner'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check'
                // Example: OWASP Dependency-Check for security scan
                // sh 'dependency-check --scan <path_to_project>'
            }
            post {
                success {
                    emailext body: Security Scan passed successfully.
                    subject: 'Security Scan Passed',
                   mail to: 'kniveditha30@gmail.com',
                    attachLog: true
                }
                failure {
                    emailext body: Security Scan failed.
                    subject: 'Security Scan Failed',
                    mail to: 'kniveditha30@gmail.com',
                    attachLog: true
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server (e.g., AWS EC2 instance)'
                // Example: AWS CLI for deploying to AWS EC2 instance
                // sh 'aws ec2 deploy ...'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
                // Example: Selenium or Postman for integration tests
                // sh 'run_integration_tests.sh'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server (e.g., AWS EC2 instance)'
                // Example: AWS CLI for deploying to AWS EC2 instance
                // sh 'aws ec2 deploy ...'
            }
        }
    }
}