pipeline{
    agent any
    triggers {
        pollSCM ('* * * * *')
    }
    stages{
        stage('SCM') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: 'pipeline1']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/trial-01/mavenrepo.git']]])
            }
        }
        stage('build'){
            steps{
                sh 'mvn package'
            }
        }
    }
    post{
        always{
             slackSend channel: 'jenkins-build'
        }
    }
}
