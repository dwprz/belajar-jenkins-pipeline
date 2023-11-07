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