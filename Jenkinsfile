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
        timeout(time: 21, unit: 'SECONDS')
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
                    echo "Branch = ${params.BRANCH_NAME}"
                    echo "Enviroment =  ${params.ENV}"
                """
                }
            }
        }

        stage ('Testing') {
            steps {
                script {
                    sh  """
                    echo "Testing is Success"
                    sleep 5
                """
                }
            }
        }

        stage ('Deploying') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Azhar', description: 'Who should I say hello to?')
                }
            }
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