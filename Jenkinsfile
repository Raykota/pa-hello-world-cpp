properties([
	pipelineTriggers([pollSCM('H/3 * * * *')])])

node (){
	cleanWs()
	checkout scm
	sh "make"
	sh "./main"
}

node() {
  stage('checkout') { checkout scm }
  stage('stage2build') { sh 'make'}
  stage('archivage') { archiveArtifacts artifacts: 'main', onlyIfSuccessful: true}
}
