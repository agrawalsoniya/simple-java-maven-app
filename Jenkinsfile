// Powered by Infostretch 

timestamps {

node () {

	stage ('RollbackGit - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/tags/$GIT_TAG']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/sumitrathi95/simple-java-maven-app.git']]]) 
	}
	stage ('RollbackGit - Build') {
 			// Maven build step
	withMaven(maven: 'Maven 3.3.9') { 
 			if(isUnix()) {
 				sh "mvn -B -DskipTests clean package " 
			} else { 
 				bat "mvn -B -DskipTests clean package " 
			} 
 		}		// Maven build step
	withMaven(maven: 'Maven 3.3.9') { 
 			if(isUnix()) {
 				sh "mvn test " 
			} else { 
 				bat "mvn test " 
			} 
 		} 
	}
}
}
