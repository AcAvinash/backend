#!groovy
// it means the libraries will be downloaded and accessible at run time
@Library('expense-shared-library') _

def configMap = [
    application: "nodeJSVM",
    component: "backend",
]
env

// this is .groovy file name and function inside it
//if not master then trigger pipeline
if ( ! env.BRANCH_NAME.equalsIgnoreCase('main')){
    pipelineDecission.decidePipleine(configMap)
}
else{
    echo "main PROD deployment should happen through CR"
}