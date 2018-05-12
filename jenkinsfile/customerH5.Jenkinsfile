@Library("pilipa-library") _

withCredentials([usernamePassword(credentialsId: 'oss-assets', passwordVariable: 'OSS_SECRET', usernameVariable: 'OSS_KEY')]){
    def buildEnv = "['NODE_ENV':'svt', 'REGION':'oss-cn-beijing-internal', 'ACCESS_KEY_ID':'${OSS_KEY}', \
            'ACCESS_KEY_SECRET':'${OSS_SECRET}', 'BUCKET':'pilipa-assets', 'FILE_DIR':'app/customerH5/']"
    microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/customer-h5',
        repoUrl: 'git@git.i-counting.cn:pilipa.cn/customer-h5.git',
        credentialsId: 'jenkins at git.i-counting.cn', branch: "dev",
        buildEnvironments: buildEnv,
        runner: 'MicroserviceCI/MicroserviceRunner',
        serviceName: 'pilipa-customer-h5')
}