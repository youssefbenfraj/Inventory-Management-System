pipeline{
  agent any
  stages{
    stage('build spring'){
      steps{
        sh 'docker build -t spring-app ./airbus-management-spring/Dockerfile'
      }
    }
     stage('deploy spring'){
      steps {
        sh 'docker run -d -p 8075:80 --name Spring spring-app'
      }
    }
  }
}
