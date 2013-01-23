mvn-repo
========

For as long we don't have an actual maven repository to upload our artifacts too, we use this.

The idea is to configure the distribution repository to a checkout of this. Like so:

    <properties>
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
This is used now in https://github.com/ibissource/ibis-servicedispatcher
  
  
The following can be added to a project that needs artifacts distributed to this repository:

    <repository>
      <id>ibis</id>
      <url>https://github.com/ibissource/mvn-repo/raw/master/releases</url>
    </repository>
    
This e.g. https://github.com/ibissource/parent because it needs the ibis-servicedispatcher.

