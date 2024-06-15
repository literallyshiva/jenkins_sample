pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/literallyshiva/jenkins_sample.git'
            }
        }

    post {
        always {
            emailext (
                to: 'shivanandt120@gmail.com',
                subject: "Jenkins Build ${currentBuild.fullDisplayName}",
                body: """<p>Build ${currentBuild.fullDisplayName} is completed.</p>
                         <p>Check console output at ${env.BUILD_URL} to view the results.</p>""",
                attachLog: true
            )
        }
    }
}
