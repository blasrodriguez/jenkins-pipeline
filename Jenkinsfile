#!groovy​
def artifact_directory = "/tmp/artifacts"
def redirect_url = 'http://nexus.beabloo.com/service/local/artifact/maven/redirect'
def mybloo_artifact = "cms-frontend"
def mybloo_group = "com.beabloo.mybloo"
def mybloo_repo = "Releases"
def engine_artifact = "BeablooEngine2"
def engine_group = "com.beabloo"
def engine_repo = "beabloo"

properties([[
    $class: 'ParametersDefinitionProperty', parameterDefinitions: [
        [$class: 'VersionParameterDefinition', artifactid: "${mybloo_artifact}", description: 'mybloo version', groupid: "${mybloo_group}", propertyName: 'mybloo_version', repoid: "${mybloo_repo}"],
        [$class: 'VersionParameterDefinition', artifactid: "${engine_artifact}", description: 'engine2 version', groupid: "${engine_group}", propertyName: 'engine2_version', repoid: "${engine_repo}"]
    ]
]])
node {
        stage ('Get Artifacts from Nexus') {
            sh "rm -rf ${artifact_directory}"
            sh "mkdir ${artifact_directory}"
            sh "curl -o $${artifact_directory}/cms-frontend.war ${redirect_url}?r=${mybloo_repo}&g=${mybloo_group}&a=${mybloo_artifact}&v=${parms.mybloo_version}&e=war"

        }
        stage('Deploy') {
            echo "Hello ${redirect_url}"
        //input message: 'Selecciona una', parameters: [[$class: 'VersionParameterDefinition', artifactid: 'cms-frontend', description: '', groupid: 'com.beabloo.mybloo', propertyName: '', repoid: 'Releases']]
        }
}
