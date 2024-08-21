pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh './mvnw clean install'
            }
        }
    }
    post {
        always {
            junit 'build/reports/**/*.xml'
        }
    }
}
