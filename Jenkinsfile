pipeline {
    agent any
    stages {        
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