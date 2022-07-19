pipeline {
    agent any
    parameters {
        string(name: "reftype", defaultValue: "", description: "GitHub REF type")
        string(name: "ref", defaultValue: "", description: "Github REF value")
    }
    triggers {
        GenericTrigger(

            genericVariables: [
                [key: 'ref', value: '$.ref', expressionType: 'JSONPath'],
                [key: 'reftype', value: '$.ref_type']
            ],
            token: 'notsosecret',
            regexpFilterText: '$ref',
            printContributedVariables: true,
            printPostContent: true,


        )
    }
    stages {
        stage("Get Environment") {
            steps {
                sh "printenv"
            }
        }
        stage("Get Variables") {
            steps {
                sh "echo $reftype"
                sh "echo $ref"
            }
        }
    }
}