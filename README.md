# A21B22C23D24E25

Publihsing new OTMM jars to the Repo:

Notes: 
- ~/Dev/psldev is the local copy of the Maven Repo
- Copy the JARS that needs to be published to Maven Repo .. Copy to local dir (e.g ~/otmm-105-jars)
********************************************************************

Generate poms and parent pom.xml
--------------------------------

> cd ~/Dev/psldev
> export RUN_TYPE=print

[Update group and version as needed] 
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/artesia/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/commons/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/otds/10.5/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/creativereview/*.jar

********************************************************************

- Create a new pom.xml with follow and save in folder  ~/otmm-105-jars/all-jars

<project>
	<modelVersion>4.0.0</modelVersion>
    <groupId>com.otmm.105</groupId>
    <artifactId>all-jars</artifactId>
    <version>10.5</version>
    <packaging>pom</packaging>
    <dependencies>
    	[ENTER DEP HERE]
    </dependencies>
</project>

- For each set of output in cmd, Copy all the dependencies into pom 
********************************************************************

> cd ~/otmm-jars/all-jars
> mvn install
> mv ~/.m2/repository/com/otmm/105/all-jars ~/Dev/psldev/com/otmm/105/


Deploy all poms to PSL DEV Repo
-------------------------------

> cd ~/Dev/psldev
> export RUN_TYPE=install

[Update group and version as needed] 
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/artesia/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/commons/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/otds/10.5/*.jar
./mvn-install-jars.sh com.otmm.105 10.5 ~/otmm-105-jars/creativereview/*.jar

********************************************************************

- Use Source Tree to Commit and Push to the PSL Maven Repo


	