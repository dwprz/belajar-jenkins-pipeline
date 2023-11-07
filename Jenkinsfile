pipeline {

    agent none

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    parameters {
        string(name: 'NAME', defaultValue: 'Guest', description: 'what is your name')
        text(name: 'DESCRIPTION', defaultValue: '', description: 'tell me about you')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'need to deploy?')
        choice(name: 'SOCIAL_MEDIA', choices: ['Instagram', 'Gmail', 'Slack'] , description: 'which social media!')
        password(name: 'SECRET', defaultValue: '', description: 'encrypt key')
    }
    
    stages {

        stage ("Paramters") {

            agent {
                node {
                    label("example-label && poseidon")
                }
            }

            steps {
                echo "hello ${params.NAME}"
                echo "your description is ${params.DESCRIPTION}"
                echo "need to deploy ${params.DEPLOY}"
                echo "your social media is ${params.SOCIAL_MEDIA}"
                echo "your secret is ${params.SECRET}"
                sh("./mvnw clean compile test-compile")
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