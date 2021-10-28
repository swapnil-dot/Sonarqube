

node{
    stage("Git cloning from BitBucket"){
        git credentialsId: '34341657-ac88-4718-b298-d2b1c4f7c4c0', url: 'https://swapnil9825@bitbucket.org/swapnil9825/notejam-mysql.git'
        
    }
    stage("SonarQube analysis"){
    environment {
        scannerHome = tool 'Sonar'
    }
        withSonarQubeEnv('Sonar'){
            sh '''sudo -tt /var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Sonar/bin/sonar-scanner \
            -D sonar.projectKey=pipeline \
            -D sonar.host.url=http://localhost:9000/ \
            -D sonar.projectBaseDir=/var/lib/jenkins/workspace/real \
            -D sonar.login=73dab91e3b71d925f9c94f3659c8e8e4495f660a \
            -D sonar.projectVersion=1.0 \
            -D sonar.sources=. \
            -D sonar.verbose=true'''
        }
    }
}




