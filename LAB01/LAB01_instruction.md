# LAB01 - Simple Virtual Port Channel

## Table of Content
- [Introduction](#Introduction)
- [Prerequisites](#Prerequisites)
- [Preparation Activities](#Preparation-Activities)

## Introduction

Virtual Port Channel (vPC) is a feature that enables the extension of a port channel across two different physical switches. The main advantage of this feature is the possibility to configure dual-homing for downstream devices to two upstream switches, without the need for a loop control mechanism such Spanning Tree Protocol.

In this first virtual lab we will learn how to configure vPC in its simplest form (single-sided vPC) and to check all the status related parameters.

## Prerequisites

- Minimum RAM: 16+ GB
- Windows, MacOS or Linux
- [Download and install GNS3](https://www.gns3.com/)
- [Download NX-OSv GNS3 appliance](https://www.gns3.com/marketplace/appliance/cisco-nx-osv)
- Download appliance required software: NX-OSv version 7.3.0 \[*]

\[*] A valid Cisco account is required

## Preparation Activities

The following steps show how to setup GNS3 LAB from scratch if you are using GNS3 directly on a Linux (Ubuntu 18.04) host, i.e. without GNS VM.

Currently I'm using GNS3 version 2.2.5.

> :warning: If you are using GNS3 VM some step can be slightly different. 

### GNS3 initial setup

Open GNS3 and go to **File>Import appliance**. Choose the path of the downloaded appliance **cisco-nxosv.gns3a** and click Open in the top right corner. If you didn't change the path while downloading the file, you should find it under **~/Downloads/**.

Select **Install the appliance on your local computer** and press **Next** twice.
If you downloaded NX-OSv software (_titanium-final.7.3.0.D1.1.qcow2_) in the **~/Downloads/** folder, you should read **Ready to install** in the status column next to **NX-OSv version 7.3.0**. If so, select it and press **Next**, then **Ok**; otherwise press the **Import** button and select downloaded software before moving forward. Click **Finish** to complete this step.

### Appliance setup

Press the **Browse switches** button. It is the icon with the parallel arrows on the left side vertical bar.

Right-click on the newly installed Nexus appliance and select **Configure template**. Under the **Network** tab fill the _Adapters_ form with the value "16" and press the **Ok* button.

### GNS3 project setup

We are ready to build the following topology:

![LAB01_Topology](images/LAB01_Topology.png)

Let's create a new GNS3 project. Go to **File>New blank project** and name this project as **TrainingNexus_LAB01_Simple-vPC**, or choose the name you prefer. Press **Ok**.

Now press the **Browse switches** button and drag-and-drop 3 times the Nexus template on the workspace.




