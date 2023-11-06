pipeline {

    agent any
    
    stages {
        
        stage ("prepare") {

            steps {
                echo "start build"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number ${env.BUILD_NUMBER}"
                echo "Node Name ${env.NODE_NAME}"
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