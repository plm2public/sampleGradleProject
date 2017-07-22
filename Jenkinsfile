pipeline {
stages{
  // Mark the code checkout 'stage'....
  stage 'Stage Checkout' {
	step {
  // Checkout code from repository and update any submodules
  checkout scm
   
}}
  stage 'Stage Build' {
	step {
  //branch name from Jenkins environment variables
  echo "My branch is: ${env.BRANCH_NAME}"


  //build your gradle flavor, passes the current build number as a parameter to gradle
  sh "./gradlew clean assemble"
  }	}
    stage 'Stage Test' {
    step {
  sh "./gradlew test "
  }}
  stage 'Stage Upload To Fabric' {
  step{
  sh "call uploadArchives -PBUILD_NUMBER=${env.BUILD_NUMBER}"
  }}
 } 
}


