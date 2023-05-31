pipeline{
    agent  any;
    stages{
        stage("Build Job TEST"){
            steps{
                build job: 'TEST JOB 1'
            }

        }
        stage("Build job jenkins"){
            steps{
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE'){
                    build job: 'jenkins', parameters: [string(name: 'NEW_MAJOR_VERSION', value: '1'), string(name: 'NEW_RELEASE_VERSION', value: '1'), string(name: 'NEW_MINOR_VERSION', value: '1')]
                }
            }
        }
        stage("Build job nitesh test"){
            steps{
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE'){
                    build job: 'niteshtest', parameters: [string(name: 'NEW_MAJOR_VERSION', value: '1.0'), string(name: 'NEXT_RELEASE_VERSION', value: '1.1'), string(name: 'NEW_MINOR_VERSION', value: '1.0.1')]
                }
            }
        }

    }
}