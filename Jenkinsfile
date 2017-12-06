pipeline {
	agent any
	stages {
	    stage('Git'){
        			steps {
        				sh 'git pull origin master'
        			}
        }
	    stage('Test'){
    			steps {
    				sh 'mvn test'
    			}
        }
	    stage('Sonar'){
    			steps {
    				sh 'mvn sonar:sonar'
    			}
    		}
		stage('Build'){
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
        stage('Tomcat'){
            steps {
                sh 'mvn tomcat:deploy'
            }
        }
	}
}