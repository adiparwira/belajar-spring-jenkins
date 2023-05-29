pipeline {
    agent {
        label "Linux && Java11"
    }
    stages {
        stage('Build'){
            steps {
                echo 'Hello Build'
            }
        }

        stage('Test'){
            steps {
                echo 'Hello Test'
                sh("error")
            }
        }

        stage('Deploy'){
            steps {
                echo 'Hello Deploy'
            }
        }
    }

    post {
        always {
            echo "I will always say Hello again"
        }

        success {
            echo "Hore success"
        }

        failure {
            echo "wow no error"
        }

        cleanup {
            echo "Don't care suucess of error"
        }
    }
}