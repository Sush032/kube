node {
  //  def app
//def build_job = build job: "vote"
//build_job_number = build_job.getNumber()
  def ret = sh(script: 'cat /var/lib/jenkins/jobs/vote/nextBuildNumber', returnStdout: true)
println ret
  environment {
  ret=cat /var/lib/jenkins/jobs/vote/nextBuildNumber
}
    stage('Clone repository') {
      

        checkout scm
    }

    stage('Update GIT') {
        
            script {
                      
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
                        //def encodedPassword = URLEncoder.encode("$GIT_PASSWORD",'UTF-8')
                        sh "git config user.email sushant.sam111@gmail.com"
                        sh "git config user.name sushant"
                        //sh "git switch master"
                      sh "cat /var/lib/jenkins/jobs/vote/nextBuildNumber"
                     //   sh "DOCKERTAG= cat /var/lib/jenkins/jobs/vote/nextBuildNumber"
                     // sh "echo $DOCKERTAG"
                        sh "cat vote-deployment.yaml"
    sh "echo $env.ret"
                        sh "sed -i 's+651233853937.dkr.ecr.us-east-1.amazonaws.com/vote-j2.*+651233853937.dkr.ecr.us-east-1.amazonaws.com/vote-j2:${env.ret}+g' vote-deployment.yaml"
                        sh "cat vote-deployment.yaml"
                        sh "git add ."
                     //   sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.ret}'"
                     sh "git commit -m 'lol'"
                        sh "git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/${GIT_USERNAME}/kube.git HEAD:vote"
      }
    }
  }
}
}
