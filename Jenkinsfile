pipeline {
    agent { label 'nodejs' }

    // Set your OCP project
    environment { APP_NAMESPACE = 'llycio-devsecops' }

    stages{

        stage('Test'){
            steps {
                sh "node test.js"
            }
        }

        stage('Deploy') {
	    steps {
		sh '''
		    oc start-build greeting-devsecops --follow --wait -n ${APP_NAMESPACE}
	    }
	}
    }
}
