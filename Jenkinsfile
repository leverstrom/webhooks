pipeline {
  agent any
  parameters {
    string(name: "ref_type", defaultValue: "", description: "REF TYPE")
    string(name: "user", defaultValue: "", description: "SENDER LOGIN")
  }
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
        echo params.ref_type
        echo params.users
      }
    }
  }
}