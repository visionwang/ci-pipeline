@Library("pilipa-library") _

withCredentials([usernamePassword(credentialsId: 'oss-assets', passwordVariable: 'OSS_SECRET', usernameVariable: 'OSS_KEY')]){
    def buildEnv = "['NODE_ENV':'svt', 'REGION':'oss-cn-beijing-internal', 'ACCESS_KEY_ID':'${OSS_KEY}', \
                                'ACCESS_KEY_SECRET':'${OSS_SECRET}', 'BUCKET':'pilipa-assets', 'FILE_DIR':'app/customerFrontend/']"
    microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/caishuiying-frontend', 
        repoUrl: 'git@git.i-counting.cn:caishuiying/customer-frontend.git',
        credentialsId: 'jenkins at git.i-counting.cn', branch: "${params.branch}",
        buildEnvironments: buildEnv,
        runner: 'MicroserviceCI/MicroserviceRunner',
        serviceName: 'pilipa-caishuiying-frontend')
}
