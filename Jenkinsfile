pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
                git branch: 'main',
                    url: 'https://github.com/AdityaK05/gradle-pipeline2.git'
            }
        }

        stage('Build Application') {
            steps {
                echo "Using Java version:"
                sh 'java -version'

                echo "Building Gradle project..."
                sh 'chmod +x gradlew'
                sh './gradlew clean build'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running application..."
                sh './gradlew run'
            }
        }
    }

    post {
        success {
            echo "BUILD SUCCESSFUL 🎉"
        }
        failure {
            echo "BUILD FAILED ❌"
        }
        always {
            echo "Pipeline execution completed."
        }
    }
}pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
            }
        }

        stage('Build Application') {
            steps {
                echo "Building Gradle project..."
                sh 'chmod +x gradlew'
                sh './gradlew clean build'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running application..."
                sh './gradlew run'
            }
        }
    }

    post {
        success {
            echo "BUILD SUCCESSFUL 🎉"
        }
        failure {
            echo "BUILD FAILED ❌"
        }
        always {
            echo "Pipeline execution completed."
        }
    }
}
