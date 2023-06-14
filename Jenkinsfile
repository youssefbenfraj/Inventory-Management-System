pipeline{
  agent any
  stages{
    stage('build spring'){
      steps{
        sh 'docker build -t spring-app ./airbus-management-spring/'
      }
    } 
    stage('build angular'){
        steps{
          sh 'docker build -t angular-app ./AirbusInventory/'
        }
      }
     stage('deploy spring'){
      steps {
        sh 'docker run -d -p 8080:80 --name SpringAirbus spring-app'
      }
    }
    stage('deploy angular'){
      steps{
        sh ' docker run -d -p 4200:80 --name AngularAirbus angular-app'
      }
    }
  }
}
