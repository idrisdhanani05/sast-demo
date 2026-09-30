node {
  stage('SCM') {
    checkout scm
  }

  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven'

    withSonarQubeEnv('SonarQube') {
      bat "\"${mvn}\\bin\\mvn.cmd\" clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=sast-demo -Dsonar.projectName=\"SAST Demo\""
    }
  }
}
