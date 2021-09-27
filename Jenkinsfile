pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                def mvnHome = tool name: 'Maven', type: 'maven'
               sh "${mvnhome}/bin/mvn package"
                withMaven(maven : 'maven 3.8.2') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven 3.8.2') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven 3.8.2') {
                    sh 'mvn deploy'
                }
            }
        }
    }
} 
