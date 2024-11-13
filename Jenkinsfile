pipeline {

  
  agent any
  stages {
    stage("build"){
      steps {
        echo 'Starting to build phase'
      }
      
    }
    
     stage("test"){
      steps {
        echo 'Starting to test phase'
      }
    }
    
     stage("deploy"){
      steps {
        echo 'Starting to deploy phase'
      }
    } 
  }
  
  post {
    always {
      
    }
    failure{
      
    }
  }

}
