pipeline {
     agent {
        node {
            label 'Agent-1'
        }
     }
      environment { 
        Course="Jenkins"
        }
      options {
        timeout(time: 10, unit: 'SECOND')  
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo 'Building..'
                        echo "Hello ${Course}"
                        sleep 10
                        env 
                    """
                }
                
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """
                        echo 'Testing..'
                        echo "Hello ${Course}"
                    """
                }
            }    
        }
        stage('Deploy') {
            steps {
                script {
                    sh """
                        echo 'Deploying..'
                        echo "Hello ${Course}"
                    """
                }
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