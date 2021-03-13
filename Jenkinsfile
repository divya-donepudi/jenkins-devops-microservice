pipeline {
  agent { docker {image 'maven:3.6.3'}}
  environment {
    dockerHome = tool 'myDocker'
    mavenHome = tool 'myMaven'
    PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }
  stages {
    stage('Build') {
        steps {
            sh 'mvn --version'
            sh 'docker version'
          
            echo "Buid"
            echo "PATH - $PATH"
            echo "BUILD_NUMBER - $env.BUILD_NUMBER"
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
