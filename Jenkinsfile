#!groovy​

pipeline {
    agent any
    parameters {
        string(name: 'namespace', defaultValue: 'prueba14', description: 'Namespace or openshift project')
        string(name: 'apiURL', defaultValue: 'https://master01.4lanr1rp12xutnpngwc0di13yb.ax.internal.cloudapp.net:8443/', description: 'Openshift API URL')
        string(name: 'DNSname', defaultValue: 'prueba14', desciption: 'Final DNS will be DNSname.staging.beabloo.com')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building .."
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
                sh "oc new-app staging -p DNS_SUFFIX=${DNSname} -n ${namespace}"
            }
        }
    }
}
