pipeline {
  agent { docker {image 'maven:3.6.3'}}
  stages {
    stage('Build') {
        steps {
            sh 'mvn --version'
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
   post {
        always {
            echo 'I am awesome. I always run always.'
        }
        success {
            echo 'I run when you are successful'
        }
        failure {
            echo 'I run when you fail'
        }
  }
}
