# PUS course setup

Step-by step description on how to set up a development environment for PUS course at LUT


## What are we going to need?

In order to start developing the RESTful web services in Java, we need to set up a few tools. You should definitely start with obtaining the following:
* Java 7 (at minimun, 8 is also fine)
* Apache Maven 3
* IntelliJ IDEA

### Setting up Java
> Feel free to skip this part if you already have Java installed in your system

1. Download the JDK from [here](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and then install 
2. Set up JAVA_HOME environmental variable as described [here](http://www.wikihow.com/Set-Java-Home)


### Setting up Maven
1. Download the Apache Maven binary from [here](http://ftp.ps.pl/pub/apache/maven/maven-3/3.2.3/binaries/apache-maven-3.2.3-bin.zip)
2. Follow the official [Installation Instructions](http://maven.apache.org/download.cgi#Installation_Instructions)
3. You can verify if Maven is working by executing `mvn --version` in the command prompt

**IMPORTANT:** Before verifying if Maven works, make sure to **always** open a new cmd/terminal window. This is because the environmental variables changes are only reflected in newly opened shells

### Getting IntelliJ IDEA

1. Download IntelliJ IDEA 14 Ultimate Edition (the left one) from [here](https://www.jetbrains.com/idea/download/)
2. Meanwhile, apply for the educational license by clicking [here] and filling in the form with your university email (`your_student_id@edu.p.lodz.pl`)
3. Install and provide your license info

# Setting up a sample Jersey project

Once you've got all the tools set up, go ahead and generate the starter project

### Generating jersey-quickstart-webapp project using Maven archetype

Choose either of the two approaches below

#### Terminal-way
1. Open the cmd/terminal and navigate to your development folder (the generation process will create a new folder under your current path)
2. Execute `mvn archetype:generate -DgroupId=pl.lodz.p.pus -DartifactId=travelgood -DarchetypeGroupId=org.glassfish.jersey.archetypes -DarchetypeArtifactId=jersey-quickstart-webapp -DinteractiveMode=false`
* a `travelgood` folder will be created in your current path
3. Open up your IntelliJ IDEA, then go `File --> Import project...`
4. Select the `travelgood` folder and click `OK`
5. Keep clicking `Next`, there's no need to change anything, *but* make sure to choose *Java 7 or up*!

#### IDE-way
1. Open up IntelliJ IDEA and go `File --> New Project...`
2. Select `Maven`, then tick `Create from archetype` and click `Add Archetype...`
3. Fill in the form with the following info and then click `OK`:
* GroupId: `org.glassfish.jersey.archetypes`
* ArtifactId: `jersey-quickstart-webapp`
* Version: `2.13`
4. Make sure the newly created archetype is selected and then click `Next`
5. Fill in the project coordinates, eg:
* GroupId: `pl.lodz.p.pus`
* ArtifactId: `travelgood`
6. Keep clicking `Next` and finish

### Adding Tomcat server to IntelliJ IDEA

Once you import the project, there's not much we can do if we do not configure IntelliJ IDEA to use a web server. We'll use Tomcat here

1. Download Apache Tomcat 7 (8 should also be fine) from [here](http://ftp.ps.pl/pub/apache/tomcat/tomcat-7/v7.0.57/bin/apache-tomcat-7.0.57.zip)
2. Unpack the zip to the desired folder (eg. `C:\Developer\servers\apache-tomcat-7.0.57`)
3. Open the IntelliJ IDEA window with your project, then go `Run -> Edit Configurations..`
4. Click the `+` sign, then choose `Tomcat Server -> Local` (you may need to expand the list)
5. Change the name at the top to something more meaningful, like "Tomcat7"
6. In the `Server` tab, click `Configure...` button
7. Make `Tomcat Home` point to the folder when you downloaded your Tomcat and then click `OK`
8. Go to the `Deployment" tab`, click on the `+` sign and select `Artifact...`
9. Choose the exploded war, eg `travelgood:war exploded`, then click `OK`
10. Click `OK` to finish setting up the server

### Verifying that the sample app works

1. Start the server by clicking the green arrow in the top right part of the window or by using `Shift+F10` shortcut
2. Your browser should fire up with the `Jersey RESTful Web Application!` greeting

## TODOs
* add some images
* add REST clients sections
* add cmd tools section








