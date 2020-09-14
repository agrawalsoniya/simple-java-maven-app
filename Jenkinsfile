pipeline {
    agent any
    tools { 
        maven 'Maven 3.3.9' 
        jdk 'jdk8'
	args '-v /root/.m2:/root/.m2' 
    }
    stages {
        stage ('Build') {
            steps {
                 sh 'mvn -B -DskipTests clean package' 
            }
        }

    }
}
