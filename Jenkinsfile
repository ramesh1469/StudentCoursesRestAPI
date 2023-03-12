pipeline {
    agent { label "docker" }
     trigger {
       POLLSCM  ("* * * * *")
     }
   stages {
      stage ("vcs") {
        steps {
         git branch:"master", url:"https://github.com/ramesh1469/StudentCoursesRestAPI.git"
      }
     }
      stage (build) {
         steps {
            sh '''
               docker image build -t ram:1.0 .
               docker image tag ram:1.0 rameshram1/ram:1.0 
               docker image push rameshram1/ram:1.0 
               '''
         }
      }
   }  
}
