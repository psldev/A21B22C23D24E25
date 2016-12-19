# A21B22C23D24E25

Publihsing new OTMM jars to the Repo:

##Notes:

- ~/Dev/psldev is the local copy of the Maven Repo
- Copy the JARS that needs to be published to Maven Repo
- Copy to local dir (e.g ~/Dev/otmm-16-jars)

--

Generate poms and parent pom.xml
--------------------------------

	> cd ~/Dev/psldev

**To INSTALL (make the Maven folders locally from JAR files)**

	> export RUN_TYPE=install`

**To INSTALL (show the XML)**

	> export RUN_TYPE=print`

*[Update group and version as needed]*

	> /mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/*.jar
	> /mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/artesia/*.jar
	> /mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/commons/*.jar
	> /mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/otds/10.5/*.jar

--

- Create a new pom.xml with follow and save in folder  ~/otmm-731-jars/all-jars
		
		<project>
			<modelVersion>4.0.0</modelVersion>
		    <groupId>com.otmm.731</groupId>
		    <artifactId>all-jars</artifactId>
		    <version>7.31</version>
		    <packaging>pom</packaging>
		    <dependencies>
		    	[ENTER DEP HERE]
		    </dependencies>
		</project>


> For each set of output in cmd, Copy all the dependencies into pom 

--

> cd ~/otmm-jars/all-jars
> mvn install
> mv ~/.m2/repository/com/otmm/731/all-jars ~/Dev/psldev/com/otmm/731/all-jars


Deploy all poms to PSL DEV Repo
-------------------------------

> cd ~/Dev/psldev
> export RUN_TYPE=install

[Update group and version as needed] 
./mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/*.jar
./mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/artesia/*.jar
./mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/commons/*.jar
./mvn-install-jars.sh com.otmm.731 7.31 ~/otmm-731-jars/otds/10.5/*.jar

********************************************************************

- Use Source Tree to Commit and Push to the PSL Maven Repo


	