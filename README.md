# IoTConnect Ubuntu Python Demos

This is a collection of demos that (should) run on any gateway running Ubuntu. 

Here is a list of gateways that have been tested:
* DELL 3200/5200


## Step 0: Pre-requisites
This demo assumes the following:
* You have an existing IotConnect account (contact the support team at info@iotconnect.io to create one.) 
* You have a github account with access to 
* You have a gateway, mouse, keyboard, and monitor with a display port cable.
* The gateway is running Ubuntu. If the device needs to be re-flashed follow [this guide](https://www.dell.com/support/manuals/en-do/dell-edge-gateway-3200/egw-3200-software-users-guide/create-bootable-usb-stick-for-restore?guid=guid-6ec73f04-322f-4795-88fa-dea90eb9e8bb&lang=en-us)

## Step 1: 
* Plug in the device using it's provided power adapter and power it on.
* Plug in your mouse, keyboard, and monitor to the gateway.
* Follow the prompts from Ubuntu to setup the OS and create a user profile. **Make sure to remember your credentials**
* Once you are on the desktop 

## Step 2: Download the demo repository
* Open the terminal and run the following command to download and unzip this repostiory:

      wget https://github.com/avnet-iotconnect/iotc-ubuntu-python-demos/archive/refs/heads/main.zip
      unzip iotc-ubuntu-python-demos-main.zip
  

## Step 2: Create a Device Template in IoTConnect
* Navigate to https://awspoc.iotconnect.io/ and enter your account credentials.
   * This will bring you to your AWS IoTConnect Dashboard.
* On the far-left side of the screen is a navy-blue toolbar, hover your cursor over the icon that looks like a processor chip and choose “Device” out of the dropdown options (shown below). 

<img src=".//media/image1.png"/>

* On the toolbar at the bottom of the page, select the “Templates” tab.

<img src=".//media/image2.png"/>

* On the Templates page, click the “Create Template” button in the top right corner of the screen. 

<img src=".//media/image3.png"/>

* Enter the following information into the Template creation page and click “Save”:

| Attribute              | Value                   |
| ---------------------- | ----------------------- |
| Template Code          | DELL3200                |
| Template Name          | DELL3200_Demo           |
| Authentication Type    | Self Signed Certificate |
| Device Message Version | 2.1                     |

* Next, click on the “Attributes” tab below the information you just entered.

<img src=".//media/image4.png"/>
 
* Enter the following information and click “Save”:

| Attribute  | Value       |
| ---------- | ----------- |
| Local Name | Placeholder |
| Data Type  | INTEGER     |

* Then, click on the "Properties" tab.

<img src=".//media/image11.png"/>

* Make sure the Data Frequency is set to 60 seconds, and click save.

<img src=".//media/image12.png"/>

## Step 3: Setup the Device in IoTConnect
* Navigate back to the “Device” menu and click on “Create Device” in the top right corner of the screen.

<img src=".//media/image5.png"/>

* Enter the following information and then click “Save and View”:
  
| Attribute    | Value         |
| ------------ | ------------- |
| Unique Id    | DELL3200Demo  |
| Display Name | DELL3200_Demo |
| Entity       | Avnet         |
| Template     | DELL3200Demo  |
 
<img src=".//media/image6.png"/>

* In the resulting page, click “Connection Info” in the top-right corner of the page.

<img src=".//media/image7.png"/>

* Click on the yellow and green certificate icon in the top-right corner of the resulting pop-up to download the zipped certificate package called “PE100_Demo-certificates.”

<img src=".//media/image8.png"/>

* Extract the certificate package folder and copy the resulting certificates folder to a USB Storage Drive (flash drive). The folder should include:
   * pk_PE100_Demo.pem
   * cert_PE100_Demo.crt