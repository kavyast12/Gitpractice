pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checkout'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat '''
                    if not exist out mkdir out
                    javac -d out Hello.java
                    if errorlevel 1 exit /b 1
                '''
            }
        }

        stage('Run') {
            steps {
                bat '''
                    java -cp out Hello
                    if errorlevel 1 exit /b 1
                '''
            }
        }
    }
    stage('Archive') {
    steps {
        archiveArtifacts artifacts: 'out/**/*.class',
                         fingerprint: true
    }
}
    

    post {
        success {
            echo 'Java application executed successfully'
        }

        failure {
            echo 'Java application execution failed'
        }

        always {
            echo 'Pipeline finished'
        }
    }
}
