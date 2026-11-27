
stage('Verify Tools') {
    steps {
        bat 'echo Computer Name: %COMPUTERNAME%'
        bat 'echo JAVA_HOME=%JAVA_HOME%'
        bat 'echo MAVEN_HOME=%MAVEN_HOME%'
        bat 'where.exe java'
        bat 'where.exe mvn'
        bat 'where.exe git'
        bat 'java -version'
        bat 'mvn -version'
        bat 'git --version'
    }
}
