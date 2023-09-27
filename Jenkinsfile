pipeline {
    
    agent any
    
    tools {
        ant 'Ant12'
        nodejs 'Node18'
    }

    
    stages {
        stage('Build with Ant12') {
            steps {
                sh 'echo "Building the project..."'
                // Use the 'Ant12' tool installation configured in Jenkins
                def antHome = tool name: 'Ant12', type: 'Ant'

                // Change to the directory where your build.xml is located
                // dir('/var/lib/jenkins/workspace/TEST/Build/') {
                    // Run the Ant build command
                    sh "${antHome}/test.java"
                }
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying the application..."'
            }
        }
    }

    
    post {
        success {
            // Notify or perform actions if the build succeeds
            echo 'Build succeeded!'
        }
        failure {
            // Notify or perform actions if the build fails
            echo 'Build failed!'
        }
    }
}
