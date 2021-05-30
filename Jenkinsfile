pipeline {

    agent any

    tools {
        maven "apache-maven-3.8.1"
        jdk "jdk-1.8"
    }

    stages {
        stage("SCM checkout") {
            steps {
                git "https://github.com/jorge4larcon/blank-java.git"
            }
        }
        stage("Build") {
            steps {
                bat "mvn -Dmaven.test.failure.ignore=true package"
            }
            post {
                success {
                    junit "target/surefire-reports/**/*.xml"
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}