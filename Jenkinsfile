pipeline {

  agent any
  parameters {
        string(name: 'VERSION', defaultValue: '7.0', description: 'id of version of my app')
        booleanParam(name: 'executeTest', defaultValue: true, description: 'boolean when i run the test cases')
  }
  tools {
    gradle 'gradle-8.11'
  }
  environment {
    NEW_VERSION = '1.0.0'
    SERVER_CREDENTIAL = credentials('server-credential')
  }

  stages {
    stage("init"){
        steps {
            echo 'Hello, this is the firs step on the pipeline.'
            script {
                gv = load "script.groovy"
            }
        }
    }
    stage("build"){
        steps {
            echo 'Starting to build phase'
            echo "Building ${NEW_VERSION} now"
            script {
                gv.buildApp()
            }
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
            script {
                gv.testApp()
            }
        }
    }
    
     stage("deploy"){
        steps {
            echo 'Starting to deploy phase'
            echo "deploying my app:${params.VERSION}"
            script {
                gv.deployApp()
            }
        }
    } 
  }
}
