pipeline {
    agent any
    stages {
        stage('Parallel Execution') {
            parallel {
                stage('Compile and Execute Task 1') {
                    steps {
                        sh 'javac Task1.java'
                        sh 'java Task1'
                    }
                }
                stage('Compile and Execute Task 2') {
                    steps {
                        sh 'javac Task2.java'
                        sh 'java Task2'
                    }
                }
            }
        }
        stage('Archive Build Outputs') {
            steps {
                archiveArtifacts artifacts: '*.class', fingerprint: true
            }
        }
        stage('Workspace Cleanup') {
            steps {
                cleanWs()
            }
        }
    }
}
