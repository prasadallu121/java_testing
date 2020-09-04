node {
stage ('SCM Checkout') {
git 'https://github.com/prasadallu121/java_testing'
}
stage ('Build Package Maven') {
sh 'mvn clean package'
}

stage('SonarQube analysis') {
  withSonarQubeEnv('sonar') {
      sh 'mvn sonar:sonar'
    }
}  
stage ('Email Notification') {
    
emailext body: '''Hi team,

Testing jenkins job

Regards,
Jenkins team''', subject: 'Jenkins test mail', to: 'prasad.allu121@gmail.com'
}
}
