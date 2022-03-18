node{
	stage('Push Image'){
    		docker.withRegistry("https://index.docker.io/v2/", "dockerhub") {
			def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
			       }
        }
}
