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
    options{
        timeout(time: 5, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Git branch')
        choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests?')
        password(name: 'DB_PASSWORD', defaultValue: '', description: 'Database password')
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
                    sleep 10
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