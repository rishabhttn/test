pipeline {
   agent any
   parameters {
    gitParameter branchFilter: 'origin/(.*)',  name: 'BRANCH', type: 'PT_BRANCH'
  }
  
  stages {
      stage('CheckOut'){
          steps{
              git 'https://github.com/rishabhttn/test.git'
          }
      }
	stage('first-stage'){
        when { anyOf { branch '*/release1/*'; branch 'master' } }
        steps{
           echo "Hello"
        }
      }
      
      stage('Sonar Analysis') {
         when { branch 'release1' }
         steps {
            echo "${env.GIT_COMMIT}"
         }
      }
   }
}
