pipeline{
    agent{
        label "node"
    }
 triggers {
  genericTrigger (
   genericVariables {
    genericVariable {
     key("VARIABLE_FROM_POST")
     value("\$.something")
     expressionType("JSONPath") //Optional, defaults to JSONPath
     regexpFilter("") //Optional, defaults to empty string
     defaultValue("") //Optional, defaults to empty string
    }
   }
   genericRequestVariables {
    genericRequestVariable {
     key("requestParameterName")
     regexpFilter("")
    }
   }
   genericHeaderVariables {
    genericHeaderVariable {
     key("X_GITHUB_NAME")
     regexpFilter("")
    }
   }
   token('notsosecret')
   tokenCredentialId('')
   printContributedVariables(true)
   printPostContent(true)
   silentResponse(false)
   regexpFilterText("\$VARIABLE_FROM_POST")
   regexpFilterExpression("aRegExp")
  )
 }
 stages {
    stage("printenv") {
        steps {
            sh "printenv"
        }
    }
    stage("showvalues") {
        steps {
            echo "$VARIABLE_FROM_POST"
        }
    }
 }
}