pipeline
{
 agent any
 stages{
  
  stage('Build Application'){
  steps{
  bat 'mvn -B -U -e -V clean -DskipTests package'
  }
   }
  stage('SonarQube Testing'){
  steps{
   bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=5cc0479542876135533a93a13e747ac0a33c4a30'
   }
    }
  stage('Deploy Application To Mulesoft Cloudhub'){
  steps{
  bat 'mvn -DskipTests package deploy -DmuleDeploy'
  }
   }   
   stage('Perform Regression Testing'){
   steps{
   bat 'C:\\Users\\PSSAIR\\AppData\\Roaming\\npm\\newman run C:\\Users\\PSSAIR\\Desktop\\newman-folder\\Fhir.postman_collection.json --disable-unicode'
   }
   }
  
  }
  
 }