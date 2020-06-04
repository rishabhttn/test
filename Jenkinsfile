pipeline {
   agent any
   parameters {
    gitParameter branchFilter: 'origin/(.*)',  name: 'BRANCH', type: 'PT_BRANCH'
  }
  
  stages {
      stage('first-stage'){
        when { anyOf { branch '*/release1/*'; branch 'master' } }
        steps{
           echo "Hello"
        }
      }
   stages {
      stage('CheckOut'){
          steps{
              git branch: "${params.BRANCH}", url: 'https://github.com/rishabhttn/test.git'
          }
      }
      stage('Sonar Analysis') {
         when { expression { params.BRANCH == 'master' } }
         steps {
            echo "${env.GIT_COMMIT}"
         }
      }
   }
}
