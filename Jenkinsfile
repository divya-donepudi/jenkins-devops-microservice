pipeline {
  agent { docker {image 'maven:3.6.3'}}
  environment {
    dockerHome = tool 'myDocker'
    mavenHome = tool 'myMaven'
    PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }
  stages {
    stage('Checkout') {
        steps {
            sh 'mvn --version'
            sh 'docker version'
          
            echo "Buid"
            echo "PATH - $PATH"
            echo "BUILD_NUMBER - $env.BUILD_NUMBER"
        }
    }
    stage('Compile') {
      steps {
        sh "mvn clean compile"
      }
    }
    stage('Test') {
        steps {
            echo "Test"
            //sh "mvn test"
        }
    }
    stage('IntegrationTest') {
         steps {
             echo "IntegrationTest"
             //sh "mvn failsafe:integration-test failsafe:verify"
         }
    }
    stage('Package') {
         steps {
             echo "Package"
             //sh "mvn failsafe:integration-test failsafe:verify"
             sh "mvn package -DskipTests"
         }
    }    
    stage('Build Docker Image') {
      steps {
        //docker build -t dpothineni/currency-exchange-devops:$env.BUILD_TAG
        script {
          dockerImage = docker.build("dpothineni/currency-exchange-devops:${env.BUILD_TAG}")
        }
      }
    }
    
    stage('Push Docker Image') {
      steps {
        //docker build -t dpothineni/currency-exchange-devops:$env.BUILD_TAG
        script {
          docker.withRegistry('','dockerhub') {
          dockerImage.push();
          dockerImage.push('latest');
          }
        }
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
