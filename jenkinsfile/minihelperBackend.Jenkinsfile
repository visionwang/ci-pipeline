@Library("pilipa-library") _

pipeline {
    agent { label 'build-server' }
    options {
        buildDiscarder(logRotator(numToKeepStr: '30', daysToKeepStr: '30'))
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        timestamps()
    }
    stages {
        stage('Initialization') {
            steps {
                script {
                    env.imageName = "pilipa/minihelper-backend"
                    env.tagId = "${BUILD_ID}"
                }
            }
        }
        stage('CI') {
            agent { label 'build-server' }
            steps {
                script {
                    def IMAGENAME = "${env.imageName}"
                    def VERSION = env.tagId
                    nodeMicroServiceRelease{
                            repoUrl = "git@git.i-counting.cn:pilipa.cn/minihelper-backend.git"
                            credentialsId = "jenkins at git.i-counting.cn"
                            imageName = IMAGENAME
                            branches = 'dev'
                            tagId = VERSION
                            workspace = pwd()
                    }
                }
            }
        }
        stage('Start') {
            agent { label 'swarm-svt-master'}
            when {
                expression { 
                    currentBuild.resultIsBetterOrEqualTo('UNSTABLE')
                } 
            }
            steps {
                script {
                    def IMAGENAME = env.imageName
                    def VERSION = env.tagId
                    build job: 'MicroserviceRunner', parameters: [string(name: 'SERVICE', value: "pilipa-minihelper-backend"), string(name: 'VERSION', value: VERSION)]
                }
            }
        }
    }
    post {
        always {
            script {
                if (currentBuild.resultIsWorseOrEqualTo('FAILURE')) {
                    emailext attachLog: true, body: '$DEFAULT_CONTENT', 
                        postsendScript: '$DEFAULT_POSTSEND_SCRIPT', 
                        presendScript: '$DEFAULT_PRESEND_SCRIPT', 
                        recipientProviders: [[$class: 'CulpritsRecipientProvider'], [$class: 'RequesterRecipientProvider']], 
                            replyTo: '$DEFAULT_REPLYTO', subject: '$DEFAULT_SUBJECT', to: '$DEFAULT_RECIPIENTS'
                }
            }
        }
    }
}