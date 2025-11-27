#!groovy
// it means the libraries will be downloaded and accessible at run time
@Library('expense-shared-library') _

def configMap = [
    application: "nodeJSVM",
    component: "catalogue"
]


// this is .groovy file name and function inside it
//if not master then trigger pipeline
if (branch == null || branch== "main") {
    pipelineDecission.decidePipleine(configMap)
} else {
    echo "Non-main branch, do something else"
}

