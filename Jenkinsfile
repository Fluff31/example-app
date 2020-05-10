node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}
	
	stage('Build image') {
		app = docker.build('Fluff31/example-app')
	}
	
	stage('Push image') {
		docker.withRegistry('https://regsitry.hub.docker.com', 'docker-hub-credentials') {
			app.push('latest')
		}
	}
}
