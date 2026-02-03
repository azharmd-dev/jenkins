pipeline {
    agent {
        node {
            label 'robomart'
        }
    }
    environment {
        Name = "Azhar"
        Country = "India"
    }
    stages {
        stage ('Building') {
            steps {
                script {
                    sh  """
                    echo "Building is Success"
                    echo $Name
                """
                }
            }
        }

        stage ('Testing') {
            steps {
                script {
                    sh  """
                    echo "Testing is Success"
                """
                }
            }
        }

        stage ('Deploying') {
            steps {
                script {
                    sh  """
                    echo "Deploying is Success"
                    echo $Country
                """
                }
            }
        }
    }
    post {
        always {
            echo "Post Message after stages"
            cleanWs()
        }
        success {
            echo "Build is success"
        }
        failure {
            echo "Build is failure"
        }
    }
    
}