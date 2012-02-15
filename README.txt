This project contains pom files intended to be used when deploying or installing
VoltDB into Maven repositories. Note that the files do NOT provide any support for
building VoltDB; you'll need to do that using methods supplied by VoltDB themselves, 
or get binary distributions for them.

The value of using the pom files defined here is that they list the transitive
dependencies required by VoltDB, meaning that setting up a project using VoltDB
in your IDE will be easier. You will still need to supply the Java library
path parameter for the native libraries.

To install server and client jars into your local repository, do:

mvn install:install-file -Dfile=path/to/voltdb.jar -DpomFile=voltdb-2.2.1.pom
mvn install:install-file -Dfile=path/to/voltdbclient.jar -DpomFile=voltdb-java-client-2.2.1.pom

To include the client jar into a project, do:

 ...
  <build>
   ...
   <dependencies>
    ...
    <dependency>
      <groupId>org.voltdb</groupId>
      <artifactId>voltdb-java-client</artifactId>
      <version>2.2.1</version>
    </dependency>
    ...
   </dependencies>
  ...
 </build>
 ...

