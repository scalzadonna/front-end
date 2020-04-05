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
                sh 'npm run tests'
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Packaging'
                sh 'npm package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
