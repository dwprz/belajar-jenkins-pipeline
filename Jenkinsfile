pipeline {

    agent any

    environment {
        AUTHOR = "Kongleong Poseidon"
        EMAIL = "kongleong.poseidon@gmail.com"
        WEB = "https://exampleweb.com"
        APP = credentials("kongleong_rahasia")
    }
    
    stages {
        
        stage ("prepare") {

            steps {
                echo "start build"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Node Name: ${env.NODE_NAME}"
                sh("./mvnw clean compile test-compile")
                echo("Author: ${AUTHOR}")
                echo("Email: ${EMAIL}")
                echo("Web: ${WEB}")
                echo "APP user: ${APP_USR}"
                echo "APP password: ${APP_PSW}" // ini tidak akan bisa mengambil password nya
                sh('echo "App password: $APP_PSW" > "rahasia.txt"') // ini bisa mengambil passwordnya
                echo "finish build"
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