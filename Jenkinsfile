node('docker') {
    checkout scm
    stage('Build') {
        docker.image('php').inside {
            sh 'vendor/bin/phpunit'
        }
    }
}
