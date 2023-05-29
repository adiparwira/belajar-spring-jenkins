pipeline {
    agent {
        label "Linux && Java11"
    }
    stages {
        stage('Hello'){
            steps {
                echo 'HelloWorld'
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