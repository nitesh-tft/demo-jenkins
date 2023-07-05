pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World from dev'
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
