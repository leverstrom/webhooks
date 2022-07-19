pipeline {
  agent any
    parameters {
        string(name: 'before', defaultValue: 'not-set', description: '')
    }
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
        echo "before:"
        echo params.before
      }
    }
  }
}