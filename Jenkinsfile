pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.8.2') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.8.2') {
                    bat 'mvn test'
                }
            }
        }


        stage ('deployment Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.8.2') {
                    bat 'mvn deploy'
                }
            }
        }
    }
}


