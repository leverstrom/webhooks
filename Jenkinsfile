pipeline {
    agent any
    parameters {
        string(name: 'ref_value', defaultValue: '', description: 'Payload ref')
        string(name: 'x_github_event', defaultValue: '', description: 'Header X-Github-Event')
        string(name:  'ref_type', defaultValue: '', description: 'Payload ref_type')
    }
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'ref_value', value: '$.ref'],
                [key: 'ref_type', value: '$.ref_type'],
            ],
            genericHeaderVariables: [
                [key: 'X-Github-Event', regexpFilter: '']

            ],
            causeString: 'Triggered by Feature branch creation',
            token: 'createBranchSecret',
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
        stage("some-step") {
            steps {
                echo "branch:$params.ref_value;type:$params.ref_type;event:$params.x_github_event"
            }
        }
    }

}