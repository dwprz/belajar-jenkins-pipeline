pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Preparation") {

            steps {
                withCredentials([usernamePassword(
                    credentialsId: "eko_rahasia",
                    usernameVariable: "USER",
                    passwordVariable: "PASSWORD"
                )]) {
                sh('echo "Release it with -u $USER -p $PASSWORD" > "release.txt"')
                }
            }

        }

        stage ("Deploy") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            steps {
                sh("./mvnw clean")
            } 
        }
    }
}