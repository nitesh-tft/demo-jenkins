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
                    def downstreamJobFullName = "demo-pipe"
                    build job: downstreamJobFullName, parameters: [string(name: 'BRANCH_NAME', value: "${env.BRANCH_NAME}")]
                }
            }
        }
    }
}
