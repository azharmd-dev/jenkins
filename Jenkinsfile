pipeline {
    agent {
        node {
            label 'robomart'
        }
    }
        stages {
            stage ('Building') {
                steps {
                    echo "Building Success"
                }
            }

            stage ('Testing') {
                steps {
                    echo "Testing Success"
                }
            }

            stage ('Deploying') {
                steps {
                    echo "Deploying Success"
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