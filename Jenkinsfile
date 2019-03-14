pipeline {
    agent any

    stages {

        stage('compile stage') {
            steps{
                withMaven(maven : 'apache-maven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage('test stage') {
            steps{
                withMaven(maven : 'apache-maven') {
                    sh 'mvn test'
                }
            }
        }

        stage('install stage') {
            steps{
                withMaven(maven : 'apache-maven') {
                    sh 'mvn install'
                }
            }
        }

    }

}
