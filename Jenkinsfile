pipeline {
    agent any

    tools {
        maven "M398"  // Make sure you have this version of Maven installed
    }

    stages {
        stage('Echo Version') {
            steps {
                echo 'Print Maven Version'
                sh 'mvn -v'  // Print Maven version
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests=true'  // Build without running tests
            }
        }

        stage('Unit Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed.'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}
