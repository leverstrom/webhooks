pipeline {
    agent any
    parameters {
        booleanParam(name: 'created', defaultValue: false)
        booleanParam(name: 'deleted', defaultValue: false)
        string(name: 'ref', defaultValue: '')
    }
    triggers {
        GenericTrigger(
            
            regexpFilterText: '',
            regexpFilterExpression: '',
            token: 'notsosecret',
            printContributedVariables: true,

            genericVariables: [
                [key: 'created', value: '$.created'],
                [key: 'deleted', value: '$.deleted'],
                [key: 'ref', value: '$.ref']
            ],

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
            }
        }
    }
}