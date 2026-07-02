pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps { 
		git branch: 'main',
                url: 'https://github.com/sachin-prog/static_website.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Successful'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment Successful"
        }

        failure {
            echo "Deployment Failed"
        }
    }
}
