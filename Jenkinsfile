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
                sh 'dotnet --version'
	        // run with node image
		sh 'node --version'    
            }
        }
    }
}
