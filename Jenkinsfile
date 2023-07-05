// Define parameter to store branch name
def branchName = 'master' // Default branch name if not provided

parameters {
    string(name: 'BRANCH_NAME', defaultValue: branchName, description: 'Branch name for downstream pipeline')
}
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Trigger Downstream Pipeline') {
            steps {
            build job: 'downstream-pipeline', parameters: [
            string(name: 'BRANCH_NAME', value: env.BRANCH_NAME)
            ], wait: true
        }
    }
}
}
