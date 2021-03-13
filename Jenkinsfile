//scripted
/*
node {
	stage('Build') {
		echo "Build"
	}
	stage('Test') {
		echo "Test"
	}
	stage('IntegrationTest') {
		echo "Integration Test"
	}
}
*/

//declarative

pipeline {
  agent any
  stages {
    stage('Build') {
        steps {
            echo "Buid"
        }
    }
    stage('Test') {
        steps {
            echo "Test"
        }
    }
    stage('IntegrationTest') {
         steps {
             echo "IntegrationTest"
         }
    }
  }
}
