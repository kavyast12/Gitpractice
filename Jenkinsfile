pipeline {
    agent any

    parameters {
        string(
            name: 'PROJECT_NAME',
            defaultValue: 'StudentManagement',
            description: 'Enter project name'
        )
    }

    environment {
        VERSION = '1.0'
    }

    stages {
        stage('Display Information') {
            steps {
                echo "Project: ${params.PROJECT_NAME}"
                echo "Version: ${env.VERSION}"
                echo "Build number: ${env.BUILD_NUMBER}"
                echo "Workspace: ${env.WORKSPACE}"
            }
        }
    }
}
