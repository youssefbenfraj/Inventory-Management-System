pipeline{
  agent any
  stages{
    stage('build spring'){
      steps{
        sh 'docker build -t spring-app ./airbus-management-spring/'
      }
    }
     stage('deploy spring'){
      steps {
        sh 'docker run -d -p 8075:80 --name Spring spring-app'
      }
    }
      stage('build angular'){
        steps{
          sh 'docker build -t angular-app ./AirbusInventory/'
        }
      }
    stage('deploy angular'){
      steps{
        sh ' docker run -d -p 4200:80 --name Angular angular-app'
      }
    }
  }
}
