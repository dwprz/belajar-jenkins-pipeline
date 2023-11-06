pipeline {

    agent {
        node {
            label "example-label && poseidon"
        }
    }
    
    stages {
        stage ("Build") {
            steps {

                script{
                    for(int i=0; i <= 10; i++) {
                        echo("script ${i}")
                    }
                }

                echo "start build"
                sh("./mvnw clean compile test-compile")
                echo "finish build"
            } 
        }
        stage ("Test") {
            steps {

                script{
                    def data = [
                        "first_name": "Kongleong",
                        "Last_name": "Poseidon"
                    ]

                    writeJSON(file: "data.json", json: data)
                }

                echo "hello, test 1"
                sh("./mvnw test")
                echo "hello, test 3"
            }
        }
        stage ("Deploy") {
            steps {
                echo "hello, deploy 1"
                sleep(5)
                echo "hello, deploy 2"
                echo "hello, deploy 3"
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