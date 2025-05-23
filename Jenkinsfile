pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {
                    echo "Starting deployment to Firebase Hosting..."
                    echo "Target project: jenkins"
                }
                sh '''
                    # Set Google Application Credentials
                    export GOOGLE_APPLICATION_CREDENTIALS=jenkins
                    # Deploy to Firebase Hosting
                    firebase deploy --only hosting --project=jenkins --non-interactive
                '''
                script {
                    echo "Deployment completed successfully!"
                }
            }
        }
    }
}