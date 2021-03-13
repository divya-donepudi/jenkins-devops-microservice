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
