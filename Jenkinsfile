pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Preparation") {

            agent {
                node {
                    label ("example-label && poseidon")
                }
            }

            stages {

                stage ("First Prepare") {
                    steps {
                        echo("hello first prepare")
                    }
                }

                stage ("Second Prepare") {
                    steps {
                        echo("hello second prepare")
                    }
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