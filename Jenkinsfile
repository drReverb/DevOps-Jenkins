pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Compiling stage'
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Testing Stage'
                    bat 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Deployment Stage'
                    bat 'mvn deploy'
                }
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scans...'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}