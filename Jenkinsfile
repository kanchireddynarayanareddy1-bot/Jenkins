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
        timeout(time: 10, unit: 'SECONDS')  
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
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