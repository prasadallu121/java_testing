node {
  stage ('SCM-Checkout') {
  git 'https://github.com/prasadallu121/java_testing'
  }
  stage ('Maven-Build') {
  def maven = tool name: 'my-maven', type: 'maven'
  sh "${maven}/bin/mvn clean package install"
  }
  stage('SonarQube-analysis') {
  def maven = tool name: 'my-maven', type: 'maven'
  withSonarQubeEnv('my-sonar') {
  sh "${maven}/bin/mvn sonar:sonar"
  }
  }
  stage("Quality Gate"){
  timeout(time: 1, unit: 'HOURS') {
  def qg = waitForQualityGate()
  if (qg.status != 'OK') {
  error "Pipeline aborted due to quality gate failure: ${qg.status}"
  }
  }
  stage ('Email-Notification') {
  emailext body: '''Hi Team,
  This is maven testing project.
  Regards,
  Jenkins Team''', subject: 'Maven Testing Project', to: 'prasad.allu121@gmail.com'
  }
}
