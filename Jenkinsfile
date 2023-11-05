pipeline {

    agent {
        node {
            label "example-label && poseidon"
        }
    }
    
    stages {
        stage ("Build") {
            steps {
                echo "hello, build 1"
                echo "hello, build 2"
                echo "hello, build 3"
            } 
        }
        stage ("Test") {
            steps {
                echo "hello, test 1"
                echo "hello, test 2"
                echo "hello, test 3"
            }
        }
        stage ("Deploy") {
            steps {
                echo "hello, deploy 1"
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