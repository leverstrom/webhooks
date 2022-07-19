pipeline {
  agent any
  parameters {
    string(name: "ref_type", defaultValue: "", description: "REF TYPE")
    string(name: "user", defaultValue: "", description: "SENDER LOGIN")
  }
  triggers {
    GenericTrigger(
     genericVariables: [
        [expressionType: 'JSONPath', key: 'owner', value: '$.repository.owner.login'],
        [expressionType: 'JSONPath', key: 'repo', value: '$.repository.name'],
        [expressionType: 'JSONPath', key: 'user', value: '$.sender.login']
     ],
    genericHeaderVariables: [
    [key: 'X-GitHub-Event', regexpFilter: '']
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
        echo env.owner
        echo params.user
      }
    }
  }
}