def branchName = 'main' // Default branch name if not provided

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
            def branchName = env.BRANCH_NAME
            def downstreamJobFullName = 'demo-pipe'
            def downstreamParams = [
                string(name: 'BRANCH_NAME', value: branchName)
            ]
            build job: downstreamJobFullName, parameters: downstreamParams
        }
    }
}


    }
}
