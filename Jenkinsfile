pipeline {
     agent {
        node {
            label 'Agent-1'
        }
     }
      environment { 
        Course="Jenkins"
        }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Course name is ${Course}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
            cleanWs()
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}