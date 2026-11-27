stage('Verify Tools') {
    steps {
        bat '''
        echo Computer Name: %COMPUTERNAME%
        echo JAVA_HOME=%JAVA_HOME%
        echo MAVEN_HOME=%MAVEN_HOME%
        echo PATH=%PATH%

        echo Checking Windows where.exe:
        C:\\Windows\\System32\\where.exe java || echo where.exe could not find Java

        echo Checking Java directly:
        "%JAVA_HOME%\\bin\\java.exe" -version || echo Java check failed

        echo Checking Maven directly:
        "C:\\Tools\\apache-maven-3.10.2\\bin\\mvn.cmd" -version || echo Maven check failed

        echo Checking Git directly:
        "C:\\Program Files\\Git\\cmd\\git.exe" --version || echo Git check failed
        '''
    }
}
