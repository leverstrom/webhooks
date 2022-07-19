pipeline {
  agent any
    parameters {
        booleanParam(name: 'created', defaultValue: false, description: '')
    }
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'created', value: '$.created']
     ],

     causeString: 'Triggered on $ref',

     token: '80077ECCE8414C53AB6FA60C',
     tokenCredentialId: '',

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false
    )
  }
  stages {
    stage("environment") {
        steps {
            sh "printenv"
        }
    }
    stage('Some step') {
      steps {
        echo "created:"
        echo params.created
      }
    }
  }
}