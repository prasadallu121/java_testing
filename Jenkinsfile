node {
stage ('SCM Checkout') {
git 'https://github.com/prasadallu121/java_testing'
}
stage ('Build Package') {
# Declaring Maven path
def maven_home = tool name: 'maven', type: 'maven'
  sh "${maven_home}/usr/share/maven clean package install"
}
}
