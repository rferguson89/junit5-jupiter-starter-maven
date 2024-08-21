pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Run the Maven build
                './mvnw clean compile'
            }
        }

        stage('Test') {
            steps {
                // Run the JUnit tests using Maven
                './mvnw test'
            }

            post {
                // Capture the test results and publish them
                always {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
    }

    post {
        // Cleanup actions or final notifications
        success {
            echo 'Build and tests succeeded.'
        }

        failure {
            echo 'Build or tests failed.'
        }
    }
}
