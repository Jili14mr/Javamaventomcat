pipeline {
  agent any
  parameters {
        choice choices: ['Dev', 'Staging', 'Production'], description: "Choose which environment to push changes to.", name: "DEPLOY_TO"
    }
  tools {
    maven any 
    parameters {
        choice choices: ['3.5.4', '3.5.6', '3.6.7'], description: "Choose which version ", name: "maven"
    }
  }
  triggers {
        pollSCM "* * * * *"
    }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
  stage ('Dev Deploy') {
      steps { 
        echo "deploying to DEV Env"
        script {
          deploy adapters: [tomcat9(credentialsId: 'd839536b-c6f6-4f3a-bf3f-6c38ed4fb6b3', path: '', url: 'http://3.238.147.187:8080/')], contextPath: null, war: ' **/*.war' 
      }
      }
    }
  }
}
    
  
    
    
