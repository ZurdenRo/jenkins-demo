pipeline {

  agent any
  environment {
    NEW_VERSION = '1.0.0'
    SERVER_CREDENTIAL = credentials('server-credential')
  }

  stages {
    stage("build"){
        steps {
            echo 'Starting to build phase'
            echo "Building ${NEW_VERSION} now"
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
            withCredentials([
                usernamePassword(credentials: 'server-credential', usernameVariable: 'USER', passwordVariable: 'PWD')
            ]){
                sh "some script to execute... ${USER}"
            }
        }
    } 
  }

}
