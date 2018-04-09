node('docker') {
    checkout scm
    docker.image('composer').inside {
        stage('Build') {
            sh "composer install"
            sh "cp .env.example .env"
            sh "php artisan key:generate"
        } 
        stage('Test') {
            sh "./vendor/bin/phpunit"
        }
    }
    sh "git tag build_${gitCommit}
}
