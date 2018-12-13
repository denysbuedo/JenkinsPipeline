node {
  echo 'Starting'
  git url: 'https://github.com/jglick/simple-maven-project-with-tests.git'
  echo 'sh def mvnHome'
  def mvnHome = tool 'M2'
  echo 'sh sentences'
  sh "${mvnHome}/bin/mvn -B verify"
}
