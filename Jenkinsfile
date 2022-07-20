pipeline {
    agent any
    parameters {
        string(name: "ref_value", defaultValue: "", description: "Payload ref")
        string(name: "x_github_event", defaultValue: "", description: "Header X-Github-Event")
        string(name: "ref_type", defaultValue: "", description "Payload ref_type")
    }
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'ref_value', value: '$.ref'],
                [key: 'ref_type', value: '$.ref_type'],
            ],
            genericHeaderVariables: [
                [key: 'X-Github-Event', regexpFilter: 'create']

            ]
            causeString: 'Triggered by Feature branch creation',
            token: 'createBranchSecret',
            tokenCredentialsId: '',

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
                echo "branch:$ref_value;type:$ref_type;event:$x_github_event"
            }
        }
    }

}