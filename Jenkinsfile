pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref_type', value: '$.ref_type'],
      [key: 'user', value: '$.sender.login']
     ],

     causeString: 'Triggered on $ref_type',

     token: 'notsosecret',
     tokenCredentialId: '',

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false,
    )
  }
  stages {
    stage('Some step') {
      steps {
        echo env.ref_type
        echo env.users
      }
    }
  }
}