node {
	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build("testproject")
	}

	stage('Deploy') {
		sh ("docker run -d -p 8086:80 testproject")
	}
	
	stage('Remove old images') {
		sh("docker rmi testproject:latest -f")
   }
}
