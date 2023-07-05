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
        script {
            def downstreamParams = [
                string(name: 'BRANCH_NAME', value: env.BRANCH_NAME)
            ]
            def downstreamJobFullName = 'FolderName/downstream-pipeline'
            def trigger = downstreamJobFullName + '/job/' + downstreamParams.BRANCH_NAME
            build job: trigger, parameters: downstreamParams
        }
    }
}


}
}
