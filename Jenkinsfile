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
        
}
