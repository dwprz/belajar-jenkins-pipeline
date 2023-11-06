pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'MINUTES')
    }
    
    stages {

        stage ("prepare") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            steps {
                echo "start build"
                sh("./mvnw clean compile test-compile")
                echo "finish build"
            } 
        }
    }

    post {
        always {
            echo "i will always, say hello again"
        }
        success {
            echo "yes, success"
        }
        failure {
            echo "oh no failure"
        }
        cleanup {
            echo "finish"
        }
    }
}