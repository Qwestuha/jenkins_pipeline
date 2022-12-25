pipeline {
    agent any


    stages {
        stage('Checkout') {
            steps {
                checkout([
                            $class: 'GitSCM',
                            branches: [[name:'main']],
                            doGenerateSubmoduleConfigurations: false,
                            extensions: [],
                            submoduleCfg: [],
                            userRemoteConfigs: [[url: 'https://github.com/Qwestuha/kuber.git', credentialsID: 'Nubes-token']]
                ])
            }
        }
        stage('Build') {
            steps {
                sh "ls"
                sh "pwd"
            }
        }

    }
    
}
