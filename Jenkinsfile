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
                [key: 'created', value: '$.created'],
                [key: 'deleted', value: '$.deleted'],
                [key: 'ref_value', value: '$.ref']
            ],
            regexpFilterText: '',
            regexpFilterExpression: '',
            token: 'notsosecret',
            tokenCredentialId: '',
            printContributedVariables: true,

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
                echo params.ref
                echo "created=${params.created};deleted=${params.deleted}"
            }
        }
        stage("Generic variables") {
            steps {
                echo "Print other variables"
                echo "$ref_value"
            }
        }
    }
}