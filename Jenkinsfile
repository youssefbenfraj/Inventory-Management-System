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
     stage('create network'){
      steps{
              sh 'docker network create AirbusNetwork || true'
      }
    }
     stage('deploy spring'){
      steps {
        sh 'docker run -d --network AirbusNetwork -p 8080:8080 --name AirbusSpring spring-app'
      }
    }
    stage('deploy angular'){
      steps{
        sh ' docker run -d --network AirbusNetwork -p 4200:80 --name AirbusAngular angular-app'
      }
    }
    
  }
}
