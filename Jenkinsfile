pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 1 
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 10
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "test-artifact",
                    version: "1.0.0",
                    type: "docker",
                    url: "http://localhost:1111",
                    digest: "6f637064707039346163663237383938",
                    label: "prod"
                )
                sleep 20
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 20
                error('Tests failed!')
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 20
            }
        }
    }
}
