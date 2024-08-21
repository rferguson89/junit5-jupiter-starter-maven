pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Run the Maven build
                sh './mvnw clean compile'
            }
        }

        stage('Test') {
            steps {
                // Run the JUnit tests using Maven
                sh './mvnw test'
            }
        }
    }

    post {
        always {
            // Capture the test results and publish them
            junit 'target/surefire-reports/**/*.xml'
        }
        
        success {
            echo 'Build and tests succeeded.'
        }

        failure {
            echo 'Build or tests failed.'
        }
    }
}
