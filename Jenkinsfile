pipeline {
      agent any
      stages {
            stage('Lint HTML.'){
                  steps {
                        sh "tidy -q -e *.html"
                  }
            }
            stage('Upload to AWS.') {
                steps {
                    withAWS(region:'us-east-1',credentials:"aws-static") {
                        s3Upload(file:'index.html', bucket:'mymahrousbucket', path:'/home/ahmed/mahrous/static/index.html')
                    }

                    sh 'echo "Hello World"'
                    sh '''
                        echo "Multiline shell steps works too"
                        ls -lah
                    '''
                  }

            }
        
      }
}
