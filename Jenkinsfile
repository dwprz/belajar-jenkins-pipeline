pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Preparation") {

            matrix {

                failFast true

                stage ("OS Setup") {

                    axes {

                        axis {
                            name "OS"
                            value "linux", "mac", "windows"
                        }

                        axis {
                            name "ARC"
                            value "32", "64"
                        }
                    }
                }
            }
            
            stages {

                stage ("OS Setup") {
                    
                    steps {
                        echo "OS Setup: ${OS} ${ARC}"
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