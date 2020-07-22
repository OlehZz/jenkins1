pipeline {
    agent any

    stages {
	stage('checkout SCM') {
		steps {
	           git branch: 'release/1.0.0', url: 'https://github.com/WiseHands/FootGo.git'
		}
	}
        stage('Build') {
            steps {
             //   agent {
    	//	 	 dockerfile {
	//			filename 'Dockerfile'
        //			additionalBuildArgs '-t footgo_build' 
	//			}
	//		}	
                echo 'Copy...'
		cp /var/lib/jenkins/workspace/'footgo 1'/src/main/resources/application.properties.example /var/lib/jenkins/workspace/'footgo 1'/src/main/resources/application.properties
		echo 'Building..'
		sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
