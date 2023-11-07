pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Deploy") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            input {
                id("Input_Deploy")
                ok("yes of course")
                submitter("dwprz, kongleong")
                parameters {
                    choice(name: 'TARGET_ENV', choices: ['DEV', 'QA', 'PROD'], description: 'we will deploy to?')
                }
            }

            steps {
                echo("Deploy to: ${TARGET_ENV}")
                sh("./mvnw clean")
            } 
        }
    }
}