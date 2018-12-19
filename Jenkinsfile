node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}

	stage('Build image'){
		app = docker.build('asafaven/example-app')
	}

	stage('Push image') {
        	/* Finally, we'll push the image into Docker Hub */

        	docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            		app.push("latest")
        	}
        }
	
}
