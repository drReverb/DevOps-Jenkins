pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Compiling stage'
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Testing Stage'
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_9_9') {
                    echo 'Deployment Stage'
                    sh 'mvn deploy'
                }
            }
        }
    }
}