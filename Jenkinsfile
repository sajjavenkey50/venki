pipeline {
	agent any
	
	stages {
      stage('Fetch Code'){
        steps {
          git branch: 'vp-rem', url: 'https://github.com/sajjavenkey50/venki.git'
        }
      }
      stage('BUILD') {
        steps {
          sh 'mvn install -DskipTests'
        }
        post {
          success {
            echo 'Archiving Artifact'
            archivingArtifacts artifacts: '**/target/*.war'
          }
        }
      }
      stage('UNIT TEST') {
        steps {
          sh 'mvn test'
        }
      }
      stage('Integration Test') {
        steps {
          sh 'mvn verify -DskipUnitTests'
        }
      }
      stage('Code Analysis') {
        steps {
          sh 'mvn checkstyle:checkstyle'
        }
      }
	}
}