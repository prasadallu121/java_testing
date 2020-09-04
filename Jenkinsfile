node {
  stage ('SCM-Checkout') {
  git 'https://github.com/prasadallu121/java_testing'
  }
  stage ('Maven-Build') {
    def maven = tool name: 'my-maven', type: 'maven'
    sh "${maven} clean package install"
  }
  stage ('Email-Notification') {
  emailext body: '''Hi Team,
  This is maven testing project.
  Regards,
  Jenkins Team''', subject: 'Maven Testing Project', to: 'prasad.allu121@gmail.com'
  }
}
