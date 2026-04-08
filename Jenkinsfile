pipeline {
	agent {label 'docker-agent'}
	stages{
		stage('Clone code'){
	    	steps {
			git 'https://github.com/pujaraamen/jenkins22.git'
		}
	}
		stage('build docker image'){
		steps{
			sh 'docker build -t mysite .'
		}
	}
		stage('run container'){
		steps{
			sh 'docker rm -f cont1 || true'
			sh 'docker run -d -p 8081:80 --name cont1 mysite'
		}
	}
}
