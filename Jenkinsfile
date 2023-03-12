pipeline {
    agent { label "docker" }
    trigger {
        POLLSCM("0 19 * * *")                                                         
    }
    stages {
        stage("vcs"){
          steps {
            git branch:"master", url:"https://github.com/ramesh1469/StudentCoursesRestAPI.git"
        }
      }
      stage("build"){
        steps {
            sh '''
                docker image build -t rr:1.0 .
                docker image tag rr:1.0 rameshram1/rr.1.0 
                docker image push rameshram1/rr.1.0
              ''' 
        }
      }
    }
}
