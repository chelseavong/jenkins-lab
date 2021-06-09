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
                    ls -a
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
            }
        }
    }
}