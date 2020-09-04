node {
  stage ('SCM-Checkout') {
  git 'https://github.com/prasadallu121/java_testing'
  }
  stage ('Maven-Build') {
  sh 'my-maven clean install package'
  }
  stage ('Email-Notification') {
  emailext body: '''Hi Team,
  This is maven testing project.
  Regards,
  Jenkins Team''', subject: 'Maven Testing Project', to: 'prasad.allu121@gmail.com'
  }
}
