pipeline {
    agent any

    parameters {
        booleanParam(name: "RUN_INTEGRATION_TESTS", defaultValue: true)
    }

    stages {
        stage('Run tests') {
            parallel {
                stage('Unit tests') {
                    steps {
                        sh './mvnw test -D testGroups=unit'
                    }
                }
                stage('Integration tests') {
                    when { expression { params.RUN_INTEGRATION_TESTS } }
                    steps {
                        sh './mvnw test -D testGroups=integration'
                    }
                }
            }
        }
        stage('Build') {
            steps {
                sh './mvnw package -D skipTests'
            }
        }
    }
}