node('docker') {
    checkout scm
    docker.image('composer').inside {
        stage('Build') {
            docker.image('composer').inside {
                sh "composer install"
                sh "cp .env.example .env"
                sh "php artisan key:generate"
            }
        } 
        stage('Test') {
            sh "./vendor/bin/phpunit"
        }
    }
}
