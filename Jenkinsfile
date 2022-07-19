pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref'],
      []
     ],
    genericHeaderVariables {
        genericHeaderVariable { key("X-GitHub-Event") regexpFilter("") } 
    },

     causeString: 'Triggered on $ref',

     token: '',
     tokenCredentialId: 'secret-token',

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
        sh "echo $ref"
        sh "echo $x_github_event"
      }
    }
  }
}