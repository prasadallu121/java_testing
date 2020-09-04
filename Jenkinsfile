node {
stage ('SCM Checkout') {
git 'https://github.com/prasadallu121/java_testing'
}
stage ('Build Package') {
  // Installing mvn package
sh 'mvn clean package'
}
}
