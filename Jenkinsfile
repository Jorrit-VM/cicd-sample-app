node {
    stage('Preparation') {
        sh '''
            if [ -n "$(docker ps -aq --filter name=^/samplerunning$)" ]; then
                docker rm -f samplerunning
            fi
        '''
    }

    stage('Build') {
        build job: 'BuildSampleApp', wait: true
    }

    stage('Results') {
        build job: 'TestSampleApp', wait: true
    }
}