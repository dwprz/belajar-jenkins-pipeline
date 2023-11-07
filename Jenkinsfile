pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Preparation") {

            parallel {

                stage ("First Prepare") {

                    agent {
                        node {
                            label ("example-label && poseidon")
                        }
                    }

                    steps {
                        echo("hello first prepare")
                    }
                }

                stage ("Second Prepare") {

                    agent {
                        node {
                            label ("example-label && poseidon")
                        }
                    }

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