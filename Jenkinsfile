pipeline {
    agent any

    stage('Deploy') {
            steps {
                script {
                    echo "Starting deployment to Firebase Hosting..."
                    echo "Target project: jenkins"
                }
                // Deploy to Firebase Hosting
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