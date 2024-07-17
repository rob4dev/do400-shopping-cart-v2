pipeline {
    agent any

    stages {
        stage('Run tests') {
            parallel {
                stage('Unit tests') {
                    steps {
                        './mvnw test -D testGroups=unit'
                    }
                }
                stage('Integration tests') {
                    steps {
                        './mvnw test -D testGroups=integration'
                    }
                }
            }
        }
    }
}