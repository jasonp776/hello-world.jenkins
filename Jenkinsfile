pipeline {
   agent any
   environment {
      GENERIC_WEBHOOK_TOKEN = credentials('helloWorldMultiBrachToken')
   }
   triggers
   {      
      GenericTrigger(
         genericVariables: [
            [key: 'userName', value: '$.userName']
         ],
         token: '5cb90505dc1b874d5d2731553f5f8f1b3499e33e',
         printContributedVariables: true,
         printPostContent: true,
         silentResponse: false
      )
   }
   stages {
      stage('Hello') {
         steps {
            sh """
               echo Hello $userName!
               echo $GENERIC_WEBHOOK_TOKEN
               """
         }
      }
   }
}