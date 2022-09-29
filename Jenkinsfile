pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "3.5.4"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Jili14mr/Javamaventomcat.git'

                // Run Maven on a Unix agent.
                sh "mvn clean install"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
       stage ('Tomcat Deploy') {
           steps { 
               echo "deploying to Tomcat server"
           script {
            deploy adapters: [tomcat9(credentialsId: 'd839536b-c6f6-4f3a-bf3f-6c38ed4fb6b3', path: '', url: 'http://3.238.147.187:8080/')], contextPath: null, war: ' **/*.war' 
  
                }
            }
        }
    }
    }
}
