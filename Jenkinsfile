pipeline{
  agent any
  
  stages{
    stage('Build'){
      steps{
        sh 'g++ -o pes1ug20cs157 pes1ug20cs157.cpp'
        build job:'PES1UG20CS157-1'
      }
    }
    stage('Test'){
      steps{
        sh './pes1ug20cs157'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deployed successfully'
      }
    }
  }
  post{
    always{
      script{
        if(currentBuild.result == 'FAILURE'){
          echo 'pipeline failed'
        }
      }
    }
  }
}
