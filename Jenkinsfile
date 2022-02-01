pipeline{
agent any
triggers {
             pollSCM('* * * * *')
   }
stages{

stage('scm'){
steps{
checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'a6f19693-5447-4f96-8481-f3faea3ff5bc', url: 'https://github.com/trial-01/mavenrepo.git']]])
     }
            }

stage('build'){
steps{
sh 'mvn package'
}
}



}  //stages close
}  // pipeline close
