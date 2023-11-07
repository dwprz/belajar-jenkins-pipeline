pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    parameters {
        booleanParam(name: "DEPLOY", defaultValue: false, description: "nedd to deploy?")
    }

    stages {

        stage ("Deploy") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            when {
                expression {
                    return params.DEPLOY
                }    
            }

            steps {
                sh("./mvnw clean")
            } 
        }
    }
}