pipeline {
	  agent none
    stages {        
        stage('Build'){   
		    agent {
			    dockerfile {
				    dir 'dockerfileDir'
				    filename 'test.Dockerfile'
				    additionalBuildArgs '--tag test:develop'
			    }
        }
            steps{
                //sh 'dotnet --version'
	        // run with node image
		//sh 'node --version'   
		// run with ubuntu
		sh 'cat /etc/lsb-release'   
            }
        }
    }
}
