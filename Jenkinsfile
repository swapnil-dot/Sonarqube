

node{
    stage("Git cloning from BitBucket"){
        git credentialsId: 'REPO_CREDENTIALS', url: '<REPO_URL>'
        
    }
    stage("SonarQube analysis"){
    environment {
        scannerHome = tool 'Sonar'
    }
        withSonarQubeEnv('Sonar'){
            sh '''sudo -tt /var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Sonar/bin/sonar-scanner \
            -D sonar.projectKey=<PROJECT_NAME_SPECIFIED_ON_SONARQUBE> \
            -D sonar.host.url=http://localhost:9000/ \
            -D sonar.projectBaseDir=/var/lib/jenkins/workspace/<PIPELINE_NAME> \
            -D sonar.login=<PROJECT_TOKEN> \
            -D sonar.projectVersion=1.0 \
            -D sonar.sources=. \
            -D sonar.verbose=true'''
        }
    }
}




