pipeline { 
    agent {
        docker {
            image 'node'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install -g node@latest --unsafe-perm'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
