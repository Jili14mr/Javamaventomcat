#!groovy



pipeline {
    agent any
    //environment {
       // S3_BUCKET_PATH = 'gpus-ops1b-infra-jenkins-log-bucket/infra-jenkins/logs'
       // KMS_KEY_ID = 'arn:aws:kms:us-east-1:325381443140:key/f3c028a6-51a1-484e-b2a7-b8794424c5ee'
    //}
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
  parameters {
        
          
          string(value: "", description: 'master', name: 'Branch')

     string(Value: "${ArtifcatFile}", description: 'Provide Value for jar file', name: 'ArtifcatFile')
    string(value: "'${UAI}", description: 'Provide Value for jar file', name: 'UAI')
    string(value: "${AppName}", description: 'Provide Value for jar file', name: 'AppName')
    string(value: "${Environment}", description: 'Provide Value for jar file', name: 'Environment')
    string(value: "${Cluster}", description: 'Provide Value for jar file', name: 'Cluster')
    string(value: "${ArtifactName}", description: 'Provide Value for jar file', name: 'ArtifactName')
}
    stages {
        stage('start'){
            steps {
                sh '''
                    echo "============ start =============="
		    
                '''
            }
        }
        
       // stage('checkout'){
            //steps{
		    //git branch: '${Branch}', url: '${Git_url2}'
             //  git branch: 'master', credentialsId: 'git_key_auth', url: 'https://github.com/niwasawa/java-hello-world-with-maven.git'
               
				//}
            
        
             
                
            
        }
        
        
        stage('Build'){
            steps {
                //git 'https://github.com/jabedhasan21/java-hello-world-with-maven'
               sh 'mvn clean install'
		
            }
       }
        
        stage('DEPLOYMENT'){
            steps {
                sh '''
               
                #!/bin/bash +x
                cd /var/lib/jenkins/workspace/${UAIName}-${AppName}-${Cluster}-${ArtifactName}-Buildjob
                cd target
                ls -alt
                
                  
                destination_Artifactory=https://artifactory.build.ge.com/artifactory/
                path=SXZZG/GPWebUtility/Applications/${UAI}/${AppName}/${Environment}/${Cluster}/${BUILD_NUMBER}/${ArtifactName}
                curl -k  --user ${artifactory_log_User}:${artifactory_log_Password} -X PUT $destination_Artifactory/$path -H 'Content-Type: application/data' --upload-file ${ArtifactName}
              
              
              
                   '''

            }
        }
        
        
        


       stage('DEPLOYMENT TO SERVER'){
            steps {
                sh '''
                    echo "============ done =============="
                '''
            }
        }
    }
    
    
}
