pipeline {

  agent any
  
  stages {
    stage("build"){
        steps {
            echo 'Starting to build phase'
        }
    }
    
     stage("test"){
        when {
            expression {
                BRANCH_NAME == 'dev'
            }
        }  
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

}
