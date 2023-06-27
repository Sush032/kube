node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Update GIT') {
        
            script {
                                      UPSTREAM=`curl "http://jenkins:8080/job/vote/lastBuild/api/xml?depth=1&xpath=/freeStyleBuild/number"`
                      NUMBER=`echo "$UPSTREAM" | sed "s/[^0-9]//g"`
                       echo $NUMBER
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
                        //def encodedPassword = URLEncoder.encode("$GIT_PASSWORD",'UTF-8')
                        sh "git config user.email sushant.sam111@gmail.com"
                        sh "git config user.name sushant"
                        //sh "git switch master"
                        sh "cat vote-deployment.yaml"
                        sh "sed -i 's+651233853937.dkr.ecr.us-east-1.amazonaws.com/vote-j2.*+651233853937.dkr.ecr.us-east-1.amazonaws.com/vote-j2:${DOCKERTAG}+g' vote-deployment.yaml"
                        sh "cat vote-deployment.yaml"
                        sh "git add ."
                        sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.BUILD_NUMBER}'"
                        sh "git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/${GIT_USERNAME}/kube.git HEAD:vote"
      }
    }
  }
}
}
