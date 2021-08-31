pipeline
{
 agent any
 stages{
  stage('Build Application'){
  steps{
  bat 'mvn clean install'
  }
   }
   
  
     
  stage('Deploy Application To Mulesoft Cloudhub'){
  steps{
  bat 'mvn package deploy -DmuleDeploy'
  }
   } 
   
   stage('Perform Regression Testing'){
   steps{
   bat 'C:\\Users\\PSSAIR\\AppData\\Roaming\\npm\\newman run C:\\Users\\PSSAIR\\Desktop\\newman-folder\\Fhir.postman_collection.json --disable-unicode'
   }
   }
   
   
 
  }
  
 }