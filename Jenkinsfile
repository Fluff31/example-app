node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}
	
	stage('Build image') {
		app = docker.build('fluff31/example-app')
	}
	
	stage('Push image') {
		docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-cred') {
			app.push('latest')
		}
	}
}
