pipeline {
    agent none

    stages {
        stage("Init") {
            agent {
                node {
                    label "linux && java11"
                }
            }
            
            steps {
                echo("Init")
            }
        } 

        stage('Scm') {
            agent {
                node {
                        label "linux && java11"
                    }
            }

            steps {
                echo("Scm")

                dir("${BRANCH}"){
                    script {
                        def date = new Date()
                        def data = "Hello World\nSecond line\n" + date
                        writeFile(file: 'zorg.txt', text: data)
                        sh "ls -l"
                        sh "cat zorg.txt"
                    }  
                }
            }
        }

        stage('Build'){
            agent {
                node {
                    label "linux && java11"
                }
            }  

            steps {
                script {
                    for (int i = 0 ; i < 10 ; i++) {
                        echo("Script ${i}")
                    }
                }
                
                echo("Start build")
                sh("./mvnw clean compile test-compile")
                echo("Finish build") 
            }
        }

        stage('Test'){
            agent {
                node {
                    label "linux && java11"
                }
            }

            steps {
                echo("Start test")
                sh("./mvnw test")
                echo("Finish test")
            }
        }

        stage('Deploy'){
            agent {
                node {
                    label "Agent || 2"
                }
            }

            steps {
                echo 'Hello Deploy 1'
                sleep(5)
                echo 'Hello Deploy 2'
                echo 'Hello Deploy 3'
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
