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
    
 // parameters {
        
          
         // string(value: "", description: 'master', name: 'Branch')

    // string(Value: "${ArtifcatFile}", description: 'Provide Value for jar file', name: 'ArtifcatFile')
    //string(value: "'${UAI}", description: 'Provide Value for jar file', name: 'UAI')
    //string(value: "${AppName}", description: 'Provide Value for jar file', name: 'AppName')
   // string(value: "${Environment}", description: 'Provide Value for jar file', name: 'Environment')
    //string(value: "${Cluster}", description: 'Provide Value for jar file', name: 'Cluster')
   // string(value: "${ArtifactName}", description: 'Provide Value for jar file', name: 'ArtifactName')
//}
    stages {
        
	stage("Read Manifest Config") {
	node {
		def configVal = readYaml file: "manifest.yml"
		sh echo "configVal: " + configVal
	}
}

    }    
        
}     


 
    
    

