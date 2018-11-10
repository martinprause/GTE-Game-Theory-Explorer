# GTE - Game Theory Explorer #

The Game Theory Explorer (by [Mark Egesdal](https://github.com/gambitproject/gte), [Alfonso](https://github.com/alfongj/gte) and [Rahul](https://github.com/rahulsavani/gte)) is a graphical user interface for interactive construction and analysis of small to medium games. The GTE is part of the [Gambit Project](http://www.gambit-project.org) - a
library of game theory software. This version of GTE is designed to be portable across plarforms and runs on Linux and Windows (Mac OS X in progress). The software consists of a Web-Application-Client for the User-Interface (written in ActionScript) and a Web-Application-Server (Jetty) to process computational tasks such as calculation and enumeration of Nash-Equilibria.

![GTE Mainwindow](https://github.com/downloads/martinprause/GTE-Game-Theory-Explorer/gte_small.png)

Test 1
## Preface ##

GTE can be installed in three different ways:

1. Compiled version (PRODUCTIVE), ready to run on an installed Jetty Server
2. Client Development version (CLIENT) for changing the GUI written in ActionScript
3. Server Development version (SERVER) for changing servlets or intergrate algorithmes written in Java or native code.


**Applied to PRODUCTIVE, CLIENT  and SERVER**

## 1. Install Java SDK ##

1. Download Java SDK (at least Java SE 6) at: [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html "Java Download")
2. Set the environment variable JAVA_HOME to the installed JAVA SDK

## 2. Install ANT ##
1. Download ANT at: [http://ant.apache.org/](http://ant.apache.org/ "ANT")
2. Extract the downloaded archive
3. Set the environment variable ANT_HOME to the extracted ANT directory
4. Add the **bin** directory to your PATH environment variable. See install instructions at: [http://ant.apache.org/manual/install.html](http://ant.apache.org/manual/install.html "Install ANT")

## 3. Install Jetty ##
**LINUX:**

1. `JETTY_VERSION=7.6.1.v20120215`
2. `wget http://download.eclipse.org/jetty/$JETTY_VERSION/dist/jetty-distribution-$JETTY_VERSION.tar.gz`
3. `tar xfz jetty-distribution-$JETTY_VERSION.tar.gz`
4. Set the environment variable JETTY_HOME to the extracted JETTY directory
5. Check Jetty with executing in jetty directory: `java -jar start.jar`
6. Access JETTY at: 127.0.0.1:8080   
7. Terminate JETTY with CTRL-C


**WINDOWS:**

1. Download JETTY Version 7.6.1 or above at: [http://download.eclipse.org/jetty/](http://download.eclipse.org/jetty/ "Jetty Download")
2. Extract archive
3. Open console and navigate to extracted directory
4. Set the environment variable JETTY_HOME to the extracted JETTY directory
5. Check Jetty with executing in jetty directory: `java -jar start.jar`
6. Access JETTY at: 127.0.0.1:8080   
7. Terminate JETTY with CTRL-C

**Applied to SERVER and CLIENT**

## 4. Install Flex SDK ##

1. Download  Flex SDK (Version 4.1A) at: [http://sourceforge.net/adobe/flexsdk/wiki/Download%20Flex%204/](http://sourceforge.net/adobe/flexsdk/wiki/Download%20Flex%204/ "FLEX SDK")
2. Extract archive
3. Set the environment variable FLEX_HOME to the extracted FLEX directory
4. Add the **bin** directory to your PATH environment variable.

By now you should have 4 environment variables: `JAVA_HOME, ANT_HOME, JETTY_HOME and FLEX_HOME` pointing to the corresponding directories.

## 5. Install Eclipse IDE##

Download Eclipse IDE (HELIOS or INDIGO) for Java EE Developpers 32-bit version at: [http://www.eclipse.org/downloads/](http://www.eclipse.org/downloads/ "Eclipse Download"). Do not use the 64-bit version or the new JUNO release of eclipse because it does not work with the FlashBuilder plugin later.

## 6. Run the PRODUCTIVE version
tba

## 7. CLIENT / SERVER version - Development process ##

The CLIENT version is only for developing the GUI. 

You do not need to execute ANT targets on the CLIENT version, because you only modify ActionScript files and Eclipse helps you to compile and test your code. Access the code from GitHub, change the GUI, submit the code back to GitHub

If you want to compile, test and run the complete GTE you need to setup the 
SERVER version. Access the code from GitHub and run the **compileComplete** ANT-target.

## 7. Setup and run the CLIENT version ##

1. Make a copy of your Eclipse installation, because you will integrate FlashBuilder - FLEX support for Eclipse, which is buggy and may harm other projects on eclipse.
2. Download and install Adobe Flash Builder 4.6. Sign up to Adobe with your student ID (this might take some days until Adobe has verified you as a student). As a student you will get Flash Builder for free.
3. Navigate to your Adobe Flash Builder install directory and go to the subdirectory **utilities**. Open and install "Adobe Flash Builder 4.6 Plugin-in Utility.exe". This will install the Flashbuilder - Flex Plugin into your Eclipse installation. 
4. Switch to Eclipse and import the GitHub repository into a new Flex-Project
5. Choose Flex 4.1A as the Flash Version (NOT 4.6). If you cannot choose 4.1A go to **Configure Flex SDK** and add the directory of the installed Flex SDK (4. Install Flex SDK) to Eclipse.
6. Choose as the primary source directory **gui-builder/src**
7. Finish the project wizard
8. Navigate in the project explorer to `gui-builder/src/les/math/games/builder/view`,  right click on Main.mxml and choose **set as default application**.
9. Delete the original *.mxml application file created by the project wizard (should be createt in gui-builder/src)
10. Run "main.mxml" 

Optional: If you see only a grey screen adjust the security settings of the FlashPlayer. Right-Click on the grey area and choose **Global settings** from the popup menu. Navigate to **Advanced** and scroll down. Click on **Trusted Location Settings** and add the directory where the Flash-File is executed to the list of trusted locations.

## 8. Run the Server version ##

**LINUX:**

Install gcc as a C-compiler (Ubuntu):

* `sudo apt-get clean`
* `sudo apt-get update`
* `sudo apt-get upgrade`
* `sudo apt-get install build-essential`

**WINDOWS:**
Download cygwin (setup.exe) from: [http://www.cygwin.com/](http://www.cygwin.com/ "Cygwin"). Start the setup.exe and install the following packages:

* **Devel:** gcc-mingw-g++ (20050522-3)
* **Devel:** gcc-mingw-core (20050522-3)
* **Devel:** libgcc1 (4.5.3-3)
* **Devel:** make (3.82.90-1)
* **Lib:** libgcc1 (4.5.3-3)

Choosing these packages implies that setup.exe detects dependencies and autmatically will install the following packages on its own:

* binutils (2.22.51-2)
* gcc-core (3.4.4-999)
* gcc-g++ (3.4.4-999)
* libintl3 (0.14.5-1)
* mingw-runtime (3.20-1)
* mingw-w32api (3.17-2)
* w32api (3.17-2)

After setup completes add the **bin** directory of your cygwin install dir (e.g. c:\cygwin\bin) to your PATH environment variable.

**LINUX and WINDOWS:**

1. Open Eclipse and import the GitHub repository into a new **Dynamic Web Project**.
2. Use "Apache Tomcat 7" as a build target to include necessary java libraries into your classpath for compiling servlet.
3. As "source directories" use **lib-algo/src** and **web-service/src**
4. Open **build.properties** and set the ANT-Variables `JETTY_HOME` and `FLEX_HOME` to your installed FLEX SDK and JETTY installation (absolute path). Please ensure that you use \ (backslash on Windows) and / (forwardslash on Linux) to seperate subfolders.
5. Go to **web-service/src** and open **config.properties**. Set the property `path.jetty` to you JETTY installation (absolute path)
6. Execute the `compileComplete` ANT-target. The target compiles the servlets, FLEX GUI, native Code, packs the compiled code into a War-file and deploys it to JETTY (**webapps**) and startes the JETTY server.
7. Access GTE at: `127.0.0.1:8080/gte`
8. Stop the JETTY server using the ANT-target **jetty-stop**

Optional: If you get an error while starting JETTY that says you do not have a Java SDK installed, please follow the instructions here: [http://wiki.eclipse.org/Jetty/Howto/Configure_JSP](http://wiki.eclipse.org/Jetty/Howto/Configure_JSP "Jetty No Java SDK Help"). In general it says that you have to add `-Dorg.apache.jasper.compiler.disablejsr199=true` to the **Jetty.xml** (JETTY 7.5.0 and prior) or uncomment this line in **start.ini** (JETTY 8.X and later).


## 9. Additional information ##

Please find additional instructions on how to include your native algorithm into the SERVER version on GitHub.
