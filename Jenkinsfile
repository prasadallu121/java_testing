node {
stage ('SCM Checkout') {
git 'https://github.com/prasadallu121/java_testing'
}
stage ('Build Package Maven') {
sh 'mvn clean package'
}
}
