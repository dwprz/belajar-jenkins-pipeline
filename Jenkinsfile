pipeline {

    agent {
        node {
            label "example-label && poseidon"
        }
    }
    
    stages {
        stage ("Build") {
            steps {
                echo "start build"
                sh("./mvnw clean compile test-compile")
                echo "finish build"
            } 
        }
        stage ("Test") {
            steps {
                echo "hello, test 1"
                sh("./mvnw test")
                echo "hello, test 3"
            }
        }
        stage ("Deploy") {
            steps {
                echo "hello, deploy 1"
                sleep(5)
                echo "hello, deploy 2"
                echo "hello, deploy 3"
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