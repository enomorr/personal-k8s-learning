pipeline {
    agent any
    tools{
        maven 'Maven 3.8.5'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                dir('worker'){
                    sh 'cd worker mvn compile'

                }
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'mvn -f worker/pom.xml Package -DskipTests'
            }
        }
    }
}
