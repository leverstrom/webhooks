pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'before', value: '$.before']
     ],

     causeString: 'Triggered on $ref',

     token: '80077ECCE8414C53AB6FA60C',
     tokenCredentialId: '',

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false,

     regexpFilterText: '$ref',
     regexpFilterExpression: 'refs/heads/' + BRANCH_NAME
    )
  }
  stages {
    stage('Some step') {
      steps {
        sh "echo $before"
      }
    }
  }
}