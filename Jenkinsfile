pipeline{
  agent any
    stages{
      stage('One'){
        steps{
          Hi...This is Monalisa
        }
      }
      stage('Two'){
        steps{
          input('Do you want to proceed ?')
        }
      }
      stage('Three'){
        when{
          not{
              branch "master"
          }
        }
        steps{ 
            echo "Hello"
        }
      }
      stage('Four'){
        parallel{
          stage('Unit test'){
            steps echo "Running the Unit test.........."
          }
          stage('Integration Test'){
            agent{
              docker{
                reuseNode false
                image 'ubuntu'
              }
            }
            steps{
               echo "Running the Integration test......"
            }
          }
        }
      }
      }
    }
}
