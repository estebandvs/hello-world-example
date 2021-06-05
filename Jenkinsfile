node ('master') {
    checkout scm
    stage('Build') {
        echo 'Building....'
        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }
    }
    stage('Test') {
        echo 'Testing....'
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
}
