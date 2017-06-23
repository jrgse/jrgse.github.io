---
layout: default
---

## Manual for Installing RGSE

RGSE can be installed as a Java project in Eclipse, and we require you use the Linux X64 operating system (We have tested on Ubuntu 12.04 and 14.04).

* * *

To run **RGSE**, The Java IDE **Eclipse** needs to support the **PDE** (Plug-in Development Environment) [[Eclipse Download Link]](http://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/kepler/SR2/eclipse-jee-kepler-SR2-linux-gtk-x86_64.tar.gz) , and JDK1.7 [[JDK Download Link]](http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html) is also required to be installed. We suppose that you have created a Java project named **AnalysisDriver**

## [](#header-2)**(1). Install Z3**

Put **libz3.so** [[Download Link]](https://github.com/jrgse/jrgse/blob/master/libz3.so), **libz3java.dylib** [[Download Link]](https://github.com/jrgse/jrgse/blob/master/libz3java.dylib), and **libz3java.so** [[Download Link]](https://github.com/jrgse/jrgse/blob/master/libz3java.so) in the directory **"/usr/lib/"**. (You can also install Z3 for Java by yourself, go to [[Z3 Website]](https://github.com/Z3Prover/z3) for reference).

## [](#header-2)**(2). Import the Jar Files**

Create a folder named **lib** in the directory **"pathToAnalysisDriver/"**, and put the auxiliary Jar files [[Download Link]](https://github.com/jrgse/jrgse/tree/master/jar_files) in the **lib**. Then, you should add all the Jar files to the **build path** of the **AnalysisDriver project** (Select all the Jar files -->Right click -->Build Path -->Add to Build Path).

## [](#header-2)**(3). Creat the Folder for JPF-nhandler**

Create a folder called **"onthefly"** in the directory **"pathToAnalysisDriver/"** (Note that such a folder is essential to run JPF-nhandler).

## [](#header-2)**(4). Import the WALA Projects**

Download the **WALA** projects [[Download Link]](https://github.com/jrgse/jrgse/tree/master/wala), and import all the wala projects to the workspace of **AnalysisDriver**. Then, add them to the dependent projects of the **AnalysisDriver project** (project-properties --> Java build path --> projects). Note that you need to configure **WALA** according to your **JDK** installation, i.e., change the value of **java_runtime_dir** in the file **com.ibm.wala.core/dat/wala.properties** to your own installed Java lib. All the downloaded wala projects have been compiled, you don't need to build them.

## [](#header-2)**(5). Create the Files for Static Analysis**

Put the file **Include.txt** [[Download Link]](https://github.com/jrgse/jrgse/blob/master/Include.txt) and the file **Exclusions.txt** [[Download Link]](https://github.com/jrgse/jrgse/blob/master/Exclusions.txt) in the directory **"pathToAnalysisDriver/src"**. Note that you should change **"bin/moti"** in the file **Include.txt** to the location of your own package, e.g., **"bin/yourPackageName"**.

## [](#header-2)**(6). Import the Setting File of RGSE**

Download the configuration file rgse.jpf [[Download Link]](https://github.com/jrgse/jrgse/blob/master/rgse.jpf), and put it in the directory **"pathToAnalysisDriver/"**.

## [](#header-2)**(7). Write the Analysis Driver**

You can download the motivation example [[Download Link]](https://github.com/jrgse/jrgse/blob/master/Example.java) and its analysis driver [[Download Link]](https://github.com/jrgse/jrgse/blob/master/TestMotiExamplewithSlicing.java) for reference. Note that you should change the following arguments with respect to your program: **symMethod**, **symMethodSig**, **classname**, and **mainClassName** in the **main** function and **classpath** in the **createArgsMotiExample** function. In addition, the implementation of function **getForwardFSAAntlr** (FSM) and function **setProperty** (Java monitor) depends on the property to be verified. It is worth noting that the **tutorials** [[Link]](tutorials) can also help you to write an analysis driver.

## [](#header-2)**(8). Run the Analysis Driver**

Build the **AnalysisDriver project**, and run it as a Java application.

## [](#header-2)**Contacts**

Please feel free to contact us if you have any problem.

*   <font color="#0000FF" size="4">rgse4java@gmail.com</font>
