pipeline {
    
    agent any

    stages {
        stage("SCM Checkout") {
            steps {
                git "https://github.com/jorge4larcon/blank-java.git"
            }
        }
        stage("Build") {
            steps {
                bat "mvn package -DskipTests"
            }
        }
    }
}