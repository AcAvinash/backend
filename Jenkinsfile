#!groovy
// Load shared library at runtime
@Library('expense-shared-library') _

// Configuration map for the pipeline
def configMap = [
    application: "nodeJSVM",
    component: "backend",
]

// Ensure env variables are accessible
env

// Safely get the branch name, default to 'main' if null
def branch = env.BRANCH_NAME ?: 'main'

// If not main branch, trigger pipeline decision; else log message
if (!branch.equalsIgnoreCase('main')) {
    pipelineDecission.decidePipleine(configMap)
} else {
    echo "main PROD deployment should happen through CR"
}
