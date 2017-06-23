---
layout: default
---
## **Manual for Installing and Running the Docker Image**

We suggest you use the **Linux** operating system and run the commands as the **root** user.

## [](#header-2)**(1). Install docker**

We suppose that you have installed the **docker** environment, otherwise please go to [this link](https://docs.docker.com/engine/installation/) for help. The docker image can be downloaded from [download link](https://1drv.ms/u/s!Amd07GCbYt_zbQZm2w2MBbXI6Zo).

## [](#header-2)**(2). Start the docker service**

<font color="#0000FF" size="4">service docker start</font>

## [](#header-2)**(3). Load the docker image**

<font color="#0000FF" size="4">docker load < rgse.tar</font>

## [](#header-2)**(4). Create the result folder**

<font color="#0000FF" size="4">mkdir /root/result</font>

## [](#header-2)**(5). Run the test scripts**

Running the test scripts downloaded from [this link](https://github.com/jrgse/jrgse). We set the time threshold to be 5 minutes in default, you can adjust it through changing the value of the time period in the running script. We take the program BMPDecoder for an example. The general command is **"./docker_runBMPDecoder arg1 arg2"**.

DFS mode: <font color="#0000FF" size="4">./ docker_runBMPDecoder 0 0</font>

Slicing mode: <font color="#0000FF" size="4">./ docker_runBMPDecoder 0 1</font>

Guiding mode: <font color="#0000FF" size="4">./ docker_runBMPDecoder 1 0</font>

## [](#header-2)**(6). Check the results**

The results are stored in the directory **"/root/result"** that you created in step 4. For example, **TestBMPwithSlicing.0.0.result**, **TestBMPwithSlicing.0.1.result**, and **TestBMPwithSlicing.1.0.result** are the result files for the **DFS** mode, **path slicing** mode, and **guiding** mode, respectively. At the bottom of the result file, you can find the detailed running statistics, e.g., the explored paths and time consumption.

## [](#header-2)**Contacts**

Please feel free to contact us if you have any problem.

*   <font color="#0000FF" size="4">rgse4java@gmail.com</font>
