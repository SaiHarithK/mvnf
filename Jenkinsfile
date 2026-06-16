pipeline {
  agent any

  tools {
    maven 'Maven'
  }
  stages {
    stage('checkout'){
      steps {        
        git branch:'main', url:'https://github.com/SaiHarithK/mvnf.git'
      }
    }

    stage('Build') {
      steps{
        sh 'mvn clean package'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('run') {
      steps{
        sh 'java -jar target/Testmvn-1.0-SNAPSHOT.jar'
      }
    }
  }

  post {
    success {echo "build success"}
    failure {echo 'fail'}
  }
}
      
    
