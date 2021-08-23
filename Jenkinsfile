node ('slave_aws') {
    stage('Clonacion Repositorio') {
        git branch: 'master',
            credentialsId: 'gitHubssh',
            url: 'git@github.com:DaniAravenaR/DVWA.git'

        sh "ls -lat"
        
    }
    stage('Test Unitarios') {
        sh 'echo "Tests passed Hola mundo"'
    }
    stage('Analisis de Codigo con Sonar') {
//        sh '$sonar_slave/sonar-scanner -Dsonar.projectKey=TestSonarQubeDani -Dsonar.source=. -D sonar.login=16fff8c574f734aba7df3f5c8728d1e1a50c83af -Dproject.settings=./sonar-project.properties'
    }
    stage('Deploy sobre EC2') {
        sh 'docker ps'
    }
    stage('Send slack notification') {
         slackSend color: 'good', message: 'Message from Jenkins Pipeline'
    }
}
