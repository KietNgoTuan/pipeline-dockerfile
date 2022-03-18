node{
	stage('Push Image'){
		sh 'cat Dockerfile'
    		docker.withRegistry("https://index.docker.io/v2/", "dockerhub") {
			def app = docker.build("kiettheo98/pipline-docker-test", '--file dockerfileDir/test.Dockerfile .').push("${env.BRANCH_NAME}")
			       }
        }
}
