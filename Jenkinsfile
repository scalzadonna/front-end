pipeline {
    agent any 
    
    tools {
      nodejs 'NodeJS v4.8.6'
    }
    
    stages {
        stage('Build') { 
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') { 
            steps {
                echo 'Testing...'
                sh 'npm run test'
            }
        }
	stage('Coverage'){
	    steps {
		echo 'Coverage reports...'
		sh 'npm run coverage'
	    }
	}
        stage('Deploy') { 
            steps {
                echo 'Packaging'
                sh 'npm run package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
