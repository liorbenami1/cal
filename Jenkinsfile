pipeline {
    agent any
    tools { 
        maven 'M3' 
        jdk 'jdk1.8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
		sh 'mvn -Dmaven.test.failure.ignore=true package'
            }
	    post {
                success {
		    sh 'echo success'
                }
            }
        }
    }
}
