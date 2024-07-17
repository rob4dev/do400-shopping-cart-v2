pipeline {
    agent any

    stages {
        stage('Run tests') {
            parallel {
                stage('Unit tests') {
                    steps {
                        sh './mvnw test -D testGroups=unit'
                    }
                }
                stage('Integration tests') {
                    steps {
                        sh './mvnw test -D testGroups=integration'
                    }
                }
            }
        }
    }
}