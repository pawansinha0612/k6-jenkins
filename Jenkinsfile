pipeline {
    agent any
    stages {
        stage('Performance Testing') {
            steps {
                echo 'Installing k6'
                sh '/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"'
                sh 'sudo chmod +x setup_k6.sh'
                sh 'sudo ./setup_k6.sh'
                echo 'Running K6 performance tests...'
                sh 'k6 run loadtests/performance-test.js'
            }
        }
    }
}
