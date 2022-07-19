pipeline {
    agent any
    parameters {
        booleanParam(name: 'created', defaultValue: false)
        booleanParam(name: 'deleted', defaultValue: false)
        string(name: 'ref', defaultValue: '')
    }
    triggers {
        GenericTrigger(
            
            token: 'notsosecret',
            printContributedVariables: true,
            regexpFilterText: '$ref',
            regexpFilterExpression: 'refs/heads/feature*',

            genericVariables: [
                [key: 'created', value: '$.created'],
                [key: 'deleted', value: '$.deleted'],
                [key: 'ref', value: '$.ref']
            ]
        )
    }
}