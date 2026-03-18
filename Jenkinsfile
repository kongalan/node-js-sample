pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/heroku/node-js-sample.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Deploy') {
            steps {
                sh 'mkdir -p /tmp/deploy'
                sh 'cp -r * /tmp/deploy'
                echo 'Deployment simulated'
            }
        }
    }

    post {
        success {
            echo 'Build zakończony sukcesem'
        }
        failure {
            echo 'Build NIE powiódł się'
        }
    }
}
