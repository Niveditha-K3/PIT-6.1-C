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
                    mail to: "kniveditha30@gmail.com",
                     body: "Unit and Integration Tests passed successfully" ,
                    subject: "Unit and Integration Tests Passed"
                    
                }
                failure {
                   mail to: "kniveditha30@gmail.com",
                   body: "Unit and Integration Tests failed" ,               
                   subject: "Unit and Integration Tests Failed"
                    
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
                      mail to: "kniveditha30@gmail.com",
                      body: "Security Scan passed successfully" ,
                    subject: "Security Scan Passed",
                    attachLog: true
                }
                failure {
                    mail to: "kniveditha30@gmail.com",
                     body: "Security Scan failed",
                    subject: "Security Scan Failed",
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
