pipeline{
  agent any
  stages {
    stage('Build'){
      steps{
        sh 'g++ task5.cpp'
        build 'PES1UG20CS091-1'
        echo 'Build stage successful'
      }
    }
    stage('Test'){
      steps{
        sh './a.out'
        echo 'Test stage successful'
        post {
          always{
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
  }
  post{
    failure{
      echo 'Pipeline Failed'
    }
  }
}

