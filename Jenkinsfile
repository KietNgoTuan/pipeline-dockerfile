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
            steps{
               docker.withRegistry('https://index.docker.io/v2/', 'dockerhub') {
		       def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
	       }
            }
        }
    }
}
