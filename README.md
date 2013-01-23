mvn-repo
========

For as long we dont' have an actual maven repository to upload our artifacts too, we use this.

The idea is to configure the distribution repository to a checkout of this. Like so:

    <properties>
       <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
       <github.maven.repository>file:///Users/michiel/github/ibissource/mvn-repo</github.maven.repository>
    </properties>

    ...

    <distributionManagement>
       <repository>
         <id>repo</id>
         <url>${github.maven.repository}/releases</url>
       </repository>
       <snapshotRepository>
         <id>snapshot-repo</id>
         <url>${github.maven.repository}/snapshots</url>
       </snapshotRepository>
     </distributionManagement>
  
  
The the following repository can be added to project that need artifacts:

    <repository>
      <id>ibis</id>
      <url>https://github.com/ibissource/mvn-repo/raw/master/releases</url>
    </repository>
    

