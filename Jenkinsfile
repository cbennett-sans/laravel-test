node('docker') {
    checkout scm
    stage('Build') {
        docker.image('composer/composer').inside {
            sh "composer install"
            sh "cp .env.example .env"
            sh "php artisan key:generate"
        }
        stage('Test') {
            sh "./vendor/bin/phpunit"
        }
    }
}
