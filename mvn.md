Useful Maven commands
=====================

Maven via apt-get
-----------------

    sudo apt-get install maven2

Common commands
---------------

    mvn clean
    mvn package
    mvn compile
    mvn prepare
    mvn assembly:single

    mvn clean package       # common

Running
-------

Note that ``org.hanworks.Runner`` should be replaced with the application entry point (aka main).
Also note that scope is limited to ``compile``

    mvn compile
    mvn exec:java -Dexec.classpathScope=compile -Dexec.mainClass=org.hanworks.Runner


Install into local repository (with example)
--------------------------------------------

    mvn install:install-file -Dfile=your-artifact-1.0.jar \
                            [-DpomFile=your-pom.xml] \
                            [-Dsources=src.jar] \
                            [-Djavadoc=apidocs.jar] \
                            [-DgroupId=org.some.group] \
                            [-DartifactId=your-artifact] \
                            [-Dversion=1.0] \
                            [-Dpackaging=jar] \
                            [-Dclassifier=sources] \
                            [-DgeneratePom=true] \
                            [-DcreateChecksum=true]

    mvn install:install-file    -DgroupId=org.xtreemfs \
                                -DartifactId=BabuDB \
                                -Dversion=0.5.6 \
                                -Dfile=BabuDB-0.5.6.jar \
                                -Dpackaging=jar \
                                -DgeneratePom=true \
                                -Djavadoc=javadoc-0.5.6.zip

