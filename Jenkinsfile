node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'c3430e8b-69de-44f5-b102-56178f6bd999', url: 'git@github.com:beeva-aidaonoro/course-cicd.git'
  }
  stage('Test') {
    sh './simplehttpserver/tests/unittests.sh ./simplehttpserver/'
  }
  stage('Package and publish') {
   sh "tar -zcvf simplehttpserver-${env.JO_NAME}-${env.BUILD_ID}.tar.gz ./simplehttpserver"
   sh "aws s3 cp simplehttpserver-${env.JOB_NAME}-${env.BUIL_ID}.tar.gz s3://clase-gendevops2-cicd-ci/"
  }
}