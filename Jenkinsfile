pipeline {

  agent any
  tools {
    string(name: 'VERSION', value: '7.0', description: 'id of version of my app')
    choice(name: 'MORE_VERSION', choices: ['1.1', '1.2', '3.0'], description: 'ids of my app able')
    booleanParam(name: 'executeTest', defaultValue: true, description: 'boolean when i run the test cases')
  }
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
                params.executeTest
            }
        }  
        steps {
            echo 'Starting to test phase with the var: executeTest always true'
        }
    }
    
     stage("deploy"){
        steps {
            echo 'Starting to deploy phase'
            echo "deploying my app:${params.MORE_VERSION}"
            echo "deploying my app:${params.VERSION}"
        }
    } 
  }
}
