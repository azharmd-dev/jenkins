pipeline {
    agent {
        node {
            label 'robomart'
        }
    }
        stages {
            stage ('Building') {
                steps {
                    script """
                        echo "Building is Success"
                    """
                }
            }

            stage ('Testing') {
                steps {
                    script """
                        echo "Testing is Success"
                    """
                }
            }

            stage ('Deploying') {
                steps {
                    script """
                        echo "Deploying is Success"
                    """
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