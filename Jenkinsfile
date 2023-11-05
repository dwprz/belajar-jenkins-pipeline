pipeline {
    agent node {
        label "example-label && poseidon" 
    }
    
    stages {
        stage ("example stage") {
            steps {
                echo "Hello Pipeline"
            } 
        }
    }
}