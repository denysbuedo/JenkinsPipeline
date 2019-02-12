node {
    try {
        stage ('Clone') {
        	echo 'shell scripts to Clone project...'
        }
        stage ('Build') {
        	echo 'shell scripts to build project...'
        }
        stage ('Tests') {
	        parallel 'static': {
	            echo 'shell scripts to run static tests...'
	        },
	        'unit': {
	            echo 'shell scripts to run unit tests...'
	        },
	        'integration': {
	            echo 'shell scripts to run integration tests...'
	        }
        }
      	stage ('Deploy') {
            echo 'shell scripts to deploy to server...'
      	}
	stage('Notification'){
	    emailext (
   		subject: "Job $JOB_NAME ${env.BUILD_NUMBER}'",
    		body: """<p>Check console output at <a href=$BUILD_URL$JOB_NAME</a></p>""",
    		to: "buedo@neuroinformatics-collaboratory.org",
    		from: "buedo@neuroinformatics-collaboratory.org"
	   )
    	}
    } catch (err) {
        currentBuild.result = 'FAILED'
        throw err
    }
}

