stage "DEV-QA"

node {
   git 'https://github.com/kzettlmeier/se441-qotd.git'

   def gradleHome = tool 'Gradle 2.11'
   sh "${gradleHome}/bin/gradle assemble uploadArchives test sonarqube"

   step([$class: 'ArtifactArchiver', artifacts: '**/*.war',
   fingerprint: true])
}
