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
            def downstreamJobName = 'NameOfDownstreamPipeline'
            def downstreamBranchName = env.BRANCH_NAME
            // Trigger downstream pipeline with branch name using REST API
            sh "curl -X POST 'http://jenkins-url/job/${downstreamJobName}/job/${downstreamBranchName}/build'"
        }
    }
}

}
}
