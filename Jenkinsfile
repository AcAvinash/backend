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

                   if (branch == null || branch.equalsIgnoreCase('main')) {
                        pipelineDecision.decidePipleine(configMap)
                    } else {
                        echo "Non-main branch or first-time build"
                    }
                }
            }
        }
    }
}
