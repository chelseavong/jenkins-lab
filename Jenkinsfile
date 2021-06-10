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
                timeout(1) {
                    sh './health-check.sh'
                }
            }
        }
    }

    post {
        always {
            echo 'pipeline finished'
        }
        success {
            echo 'woo u did it'
        }
        failure {
            echo 'ALERT ALERT ALERT'
        }
        unstable {
            echo 'hmm.. might wanna take a look at the pipeline'
        }
        changed {
            echo 'some things have changed'
        }
    }
}