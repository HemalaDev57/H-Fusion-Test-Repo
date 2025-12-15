pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 5
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 5
                    }
                }
            }
        }
        stage('CI') {
            parallel {
                stage('Test') {
                    steps {
                        echo 'Test...'
                        sleep 5
                    }
                }
                stage('Lint') {
                    steps {
                        echo 'Lint...'
                        sleep 5
                    }
                }
                stage('Scan') {
                    steps {
                        echo 'Scan...'
                        sleep 5
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
                sleep 5
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 5
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 5
            }
        }
    }
}
