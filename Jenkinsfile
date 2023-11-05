pipeline {

    agent {
        node {
            label "example-label && poseidon"
        }
    }
    
    stages {
        stage ("Build") {
            steps {
                echo "hello, build"
            } 
        }
        stage ("Test") {
            steps {
                echo "hello, test"
            }
        }
        stage ("Deploy") {
            steps {
                echo "hello, deploy"
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