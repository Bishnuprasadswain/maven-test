// pipeline{
//  tools{
//         jdk 'JAVA_HOME'
//         maven 'M2_HOME'
//     }
//      agent any
	  
// 	  stages{
	  
// 	  stage("checkout"){
// 	   steps{
// 	   git 'https://github.com/Bishnuprasadswain/maven-test.git'
//            //git 'https://github.com/ashisnishanka/maven-test.git'
// 	   }
// 	                  }
	
// 	   stage("compile"){
// 	    steps{
// 		 sh 'mvn compile'
// 		}
// 		}
//        stage("test"){
// 	    steps{
// 		 sh 'mvn test'
// 		}
// 		}
	
//        stage("package"){
// 	    steps{
// 		 sh 'mvn clean package'
//                  sh "mv target/*.jar target/myweb.jar"

// 		}
// 		}
// stage(backup)
// 		  {
//   steps{

// 	nexusArtifactUploader artifacts: [[artifactId: 'app', classifier: '', file: 'target/myweb.jar', type: 'jar']], credentialsId: 'NEXUS1', groupId: 'com.idream', nexusUrl: '3.108.217.68:8081/repository/maven-releases/', nexusVersion: 'nexus2', protocol: 'http', repository: 'maven-releases', version: '1.1'
	  
//   }
	
// }
// 	}
// 	}
pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('theproject')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=tokensonar -Dsonar.projectName='theproject'"
	 }
	}
  }
 }
}
