pipeline {
    agent any

    environment {
        GOOGLE_APPLICATION_CREDENTIALS = credentials('jenkins2')
    }

    stages {
        stage('Deploy') {
            steps {
                script {
                    echo "Starting deployment to Firebase Hosting..."
                    echo "Target project: jenkins-1aca6"
                }
                // Deploy to Firebase Hosting
                sh '''
                    # Set Google Application Credentials
                    export GOOGLE_APPLICATION_CREDENTIALS=${GOOGLE_APPLICATION_CREDENTIALS}
                    # Deploy to Firebase Hosting
                    firebase deploy --only hosting --project=jenkins-1aca6 --non-interactive
                '''
                script {
                    echo "Deployment completed successfully!"
                }
            }
        }
    }
}
