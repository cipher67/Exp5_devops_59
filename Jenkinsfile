pipeline {
    agent any
    tools {nodejs "LatestNode"}
    stages {
        stage('Install npm packages') {
            steps {
                sh 'npm install'
            }
        }       
        stage('Build project') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Deploy to IIS') {
            steps {
                sh 'rsync -avz build/ user@remote_host:/var/www/html/react-site'
                
                // Explanation of rsync options:
                // -a: Archive mode, which preserves permissions and other attributes
                // -v: Verbose output
                // -z: Compresses the data during transfer
                // build/: Source directory to copy from
                // user@remote_host:/var/www/html/reactApp: Destination directory to copy to
            }
        }
    }
}
