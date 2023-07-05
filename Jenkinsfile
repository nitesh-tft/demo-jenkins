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
                    build job: 'demo-pipe', parameters: [string(name: 'BRANCH_NAME', value: "${env.GIT_BRANCH}")]
                }
            }
        }
    }
}
