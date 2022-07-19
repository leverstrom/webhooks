pipeline {
    agent any
    // parameters {
    //     booleanParam(name: 'created', defaultValue: false)
    //     booleanParam(name: 'deleted', defaultValue: false)
    //     string(name: 'ref', defaultValue: '')
    // }
    triggers {
        GenericTrigger(
            
        genericVariables: [
        [key: 'pushedByName', value: '$.repository.owner.name'],
        [key: 'pushedByEmail', value: '$.repository.owner.email'],
        [key: 'commits', value: '$.before']
        ],
        causeString: 'source code push',
        token: '80077ECCE8414C53AB6FA60C',
        tokenCredentialId: '',
        printContributedVariables: true,
        printPostContent: true,
        silentResponse: false
        )
    }
    stages {
        stage("environment") {
            steps {
                sh "printenv"
            }
        }
        stage("variables") {
            steps {
                // echo params.ref
                // echo "created=${params.created};deleted=${params.deleted}"
                echo "$commits"
            }
        }
        stage("Generic variables") {
            steps {
                echo "Print other variables"
                echo "$pushedByName"
            }
        }
    }
}