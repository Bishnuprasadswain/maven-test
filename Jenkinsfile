pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('sonarenv')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=tokensonar -Dsonar.projectName='theproject'"
	 }
	}
  }
 }
}
