pipeline {
  
  agent any
  
  environment {
  	//adding a comment for the commit test
  	M2SETTINGS = "C:\\Users\\Sayantan\\.m2\\mysettings.xml"
  }
  
  stages {
	  stage('Build') {
		  steps {
		  	bat 'mvn -B -U -e -V clean -gs %M2SETTINGS% -DskipTests package'
		  }
	  }
	  stage('Deploy To Exchange') {
		  steps {
		  	bat 'mvn -B -U -e -V clean -gs %M2SETTINGS% -DskipTests deploy'
		  }
	  }
	  stage('Deploy To Dev') {
		  steps {
		  	bat 'mvn -B -U -e -V -gs %M2SETTINGS% -DskipTests deploy -DmuleDeploy'
		  }
	  }
  }
}