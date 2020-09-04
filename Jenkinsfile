node {
  stage ('SCM-Checkout') {
  git 'https://github.com/prasadallu121/java_testing'
  }
  stage('SonarQube-analysis') {
  def maven = tool name: 'my-maven', type: 'maven'
  withSonarQubeEnv('my-sonar') {
  sh "${maven}/bin/mvn sonar:sonar"
  }
  }
  stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
            }
          }
  stage ('Maven-Build') {
  def maven = tool name: 'my-maven', type: 'maven'
  sh "${maven}/bin/mvn clean package install"
  }
  stage ('Email-Notification') {
  emailext body: '''Hi Team,
  This is maven testing project.
  Regards,
  Jenkins Team''', subject: 'Maven Testing Project', to: 'prasad.allu121@gmail.com'
  }
}
