pipeline{
    agent {
        label 'master'
    }
    stage('PRINT'){
        steps{
            sh 'echo $JOB_NUMBER'
        }
    }
    stage('WRITE'){
        steps{
            sh 'echo $BUILD_NUMBER >> build_number'
        }
    }
    stage{'READ'}{
        steps{
            sh 'cat build_number'
        }
    }
    post{
        success{
            archiveArtifacts artifacts: 'build_number', fingerprint: true
        }
    }
}