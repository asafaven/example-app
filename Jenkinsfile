node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}

	stage('Build image'){
		app = docker.build('asafaven/example-app')
	}

	stage('Push image'){
		docker.withResigtry('https:://registry.hub.docker.com', 'docker-hub-credentioals'){
			app.push('latest')
		}
	}
	
}
