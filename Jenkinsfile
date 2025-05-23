pipeline {
    agent any

    environment {
        GOOGLE_APPLICATION_CREDENTIALS = credentials('jenkins2')
    }

    stages {
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'jenkins2', variable: 'FIREBASE_JSON')]) {
                    sh '''
                        echo "Using Firebase credentials from $FIREBASE_JSON"
                        cp "$FIREBASE_JSON" "$GOOGLE_APPLICATION_CREDENTIALS"

                        # Deploy to Firebase Hosting
                        firebase deploy --only hosting --project=jenkins --non-interactive
                    '''
                }
                script {
                    echo "✅ Deployment completed successfully!"
                }
            }
        }
    }
}
