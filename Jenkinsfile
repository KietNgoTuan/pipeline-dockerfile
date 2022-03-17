pipeline {
	  agent none
    stages {        
        stage('Build'){   
		    agent {
			    dockerfile {
				    dir 'dockerfileDir'
				    filename 'test.Dockerfile'
			    }
        }
	environment { 
                DOCKER_HUB_CRED = credentials('dockerhub') 

        }
            steps{
		script {
			docker.withRegistry('https://index.docker.io/v2/', '${env.DOCKER_HUB_CRED}') {
		       		def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
	       		}
		}
               
            }
        }
    }
}
