pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    stages{
    stage('maven clean'){
        steps{
          sh  'mvn clean'
        }
    }
    stage('maven install'){
        steps{
           sh 'mvn install'
        }
    }
    stage('maven package'){
        steps{
          sh  'mvn package'
        }
    }
    stage('upload artifact'){
        steps{
             nexusArtifactUploader artifacts: [[artifactId: 'bioMedical',
              classifier: '',
               file: 'target/bioMedical-0.0.1-SNAPSHOT.jar', 
               type: 'jar']], credentialsId: 'NexusID',
                groupId: 'qa', 
                nexusUrl: '18.235.233.18:8081', 
                nexusVersion: 'nexus3',
                 protocol: 'http',
                 repository: 'geolocation', 
                 version: '0.0.1-SNAPSHOT'
        }
    }
    }
}