node {
   //def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git env.gitpath
            // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.
      //mvnHome = tool 'M3'
   }
   stage('Build') {
      // Run the maven build
      //withEnv(["MVN_HOME=$mvnHome"]) {
         //if (isUnix()) {
            sh './mvnw -Dmaven.test.failure.ignore clean package'
         //} else {
            //bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
         //}
      //}
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
      stage('Build1') {
         build job: '/freestyle-petclinic/', quietPeriod: 50
      }

}
