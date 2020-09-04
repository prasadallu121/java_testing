node {
stage ('SCM Checkout') {
git 'https://github.com/prasadallu121/java_testing'
}
stage ('Build Package') {
sh 'mvn clean package install'
}
}
