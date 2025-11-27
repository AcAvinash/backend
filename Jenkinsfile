@Library('expense-shared-library') _

pipeline {
    agent any

    environment {
        // Env variables accessible here
        APP = 'nodeJSVM'
        COMPONENT = 'backend'
    }

    stages {
        stage('Decide Pipeline') {
            steps {
                script {
                    def configMap = [
                        application: env.APP,
                        component: env.COMPONENT,
                    ]

                    // Safely get the branch name, default to 'main' if null
                    def branch = env.BRANCH_NAME ?: 'main'

                    if (!branch.equalsIgnoreCase('main')) {
                        echo "Non-main branch detected: ${branch}, triggering pipeline decision..."
                        pipelineDecission.decidePipleine(configMap)
                    } else {
                        echo "main PROD deployment should happen through CR"
                    }
                }
            }
        }
    }
}
