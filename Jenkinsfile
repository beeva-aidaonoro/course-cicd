node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'c3430e8b-69de-44f5-b102-56178f6bd999', url: 'git@github.com:beeva-aidaonoro/course-cicd.git'
  }
  stage('Test') {
    sh './simplehttpserver/tests/nittests.sh ./simplehttpserver/'
  }
}