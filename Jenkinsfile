pipeline {
    agent {
        node {
            label "example-label && poseidon"
        }
    }
    
    stages {
        stage ("example stage") {
            steps {
                echo "Hello Pipeline"
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