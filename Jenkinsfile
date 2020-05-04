pipeline {
    agent any
    stages { 
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
            
        }

        stage('Upload to AWS') {
            steps {
                withAWS(credentials:'aws-static') {
                    withAWS(region:'us-east-1') {
                        s3Upload(file:'index.html', bucket:'mystaticbucket0503', path:'index.html')
                    } 
                } 
            }
        }

    }
}