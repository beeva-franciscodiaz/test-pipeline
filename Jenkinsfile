pipeline {
    agent {
        'global'
    }
    stages {
        stage('PRINT') {
            steps {
                sh 'echo i $JOB_NAME'
            }
        }
        stage('WRITE') {
            steps {
                sh 'echo $BUILD_NUMBER >> build_number'
            }
        }
        stage('READ') {
            steps {
                sh 'cat build_number'
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'build_number', fingerprint: true
        }
    }
}
