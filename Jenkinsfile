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
            sh 'curl --upload-file target/bioMedical-0.0.2-SNAPSHOT.jar -u admin:devops -v http://ec2-18-235-233-18.compute-1.amazonaws.com:8081/repository/geolocation/'
        }
    }
    }
}