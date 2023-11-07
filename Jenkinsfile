pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    parameters {
        booleanParam(name: "DEPLOY", defautlValue: false, description: "nedd to deploy?")
    }

    stages {

        stage ("Deploy") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            when {
                expressions {
                    return params.DEPLOY
                }    
            }

            steps {
                echo("Deploy to: ${TARGET_ENV}")
                sh("./mvnw clean")
            } 
        }
    }
}