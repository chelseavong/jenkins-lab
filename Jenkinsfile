pipeline {
    agent {
        docker { image 'python:3.5.1' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'python --version'
                sh 'echo "Hello World"'
                sh '''
                    echo "multi line shell script"
                    ls -lah
                '''
            }
        }

        stage("Test") {
            steps {
                echo 'Testing'
            }
        }

        stage("Deploy") {
            steps {
                echo 'Deploying'
                retry(3) {
                    sh './file.sh'
                }
            }
        }
    }
}