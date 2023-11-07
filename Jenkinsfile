pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {

        stage ("Preparation") {

            matrix {

                    axes {

                        axis {
                            name "OS"
                            values "linux", "mac", "windows"
                        }

                        axis {
                            name "ARC"
                            values "32", "64"
                        }
                    }

                    excludes {
                        exclude {
                            axis {
                                name "OS"
                                values "mac"
                            }

                            axis {
                                name "ARC"
                                values "32"
                            }
                        }
                    }

                    stages {

                        stage ("OS Setup") {

                            agent {
                                node {
                                    label("example-label && poseidon")
                                }
                            }
                                    
                            steps {
                                echo "OS Setup: ${OS} ${ARC}"
                            }
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