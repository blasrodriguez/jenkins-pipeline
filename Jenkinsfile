#!groovy​
pipeline {
    agent any
    parameters {
        string(name: 'namespace', defaultValue: 'prueba14', description: 'Namespace or openshift project')
        string(name: 'apiURL', defaultValue: 'https://openshift.beabloo.com:8443/', description: 'Openshift API URL')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building ${miVariable}.."
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                com.openshift.jenkins.plugins.pipeline.OpenShiftDeployer(apiURL, deploymentConfig, namespace, '', '')
            }
        }
    }
}
