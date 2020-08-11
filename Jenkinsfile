pipeline {
    agent { docker { image 'bryandollery/alpine-docker' } }
    options {
        skipStagesAfterUnstable()
    }
    stages {
    stage('CreateDockerFile'){
	    steps {
		script {
			writeFile file: '/Dockerfile', text: 'FROM bryandollery/alpine-docker'
			writeFile file: '/Dockerfile', text: 'RUN echo  "<BuilderName>Omar Bazaid</BuilderName>" >> /Manifest.txt'
			writeFile file: '/Dockerfile', text: 'RUN echo  "<BuildNumber>${BUILD_NUMBER}</BuildNumber>" >> /Manifest.txt'
			writeFile file: '/Dockerfile', text: 'RUN echo  "<DateTime>$(date)</DateTime>" >> /Manifest.txt'
			
		}
	}

	}
   stage('BuildDockerfile') {
            steps {
		sh "docker build --tag omar:/${BUILD_NUMBER ./}"
            }
        }
        }
}
