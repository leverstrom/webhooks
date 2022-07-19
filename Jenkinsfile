pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref_type']
     ],

     causeString: 'Triggered on $ref',

     token: 'notsosecret',
     tokenCredentialId: '',

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false,

     regexpFilterText: '$ref_type',
     regexpFilterExpression: 'refs/heads/' + BRANCH_NAME
    )
  }
  stages {
    stage('Some step') {
      steps {
        sh "echo $ref"
      }
    }
  }
}