pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'g++ new.cpp -o PES2UG20CS326-1'
        echo 'Build Successful'
      }
    }
    stage('Test') {
      steps {
        sh './PES2UG20CS326-1'
        echo 'Testing Successful'
      }
    }
    stage('Deploy') {
      when {
        expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS' 
        }
      }
      steps {
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
