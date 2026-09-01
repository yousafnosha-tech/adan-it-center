pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-ssh',
                    url: 'git@github.com:yousafnosha-tech/adan-it-center.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Adan IT Center Website...'
                sh 'test -f index.html'
            }
        }

        stage('Verify') {
            steps {
                echo 'Website files verified successfully.'
                sh 'ls -la'
            }
        }
    }

    post {
        success {
            echo 'Jenkins Build Successful!'
        }
        failure {
            echo 'Jenkins Build Failed!'
        }
    }
}
