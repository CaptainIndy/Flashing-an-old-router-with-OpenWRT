# Flashing-an-old-router-with-OpenWRT
**Overview**

OpenWrt is an open source software firmware. Flashing your router allows for enhanced security and additional upgrades from the Openwrt community.

Disclaimer: by using OpenWrt on an router voids any existing warranty on the router itself. There is also a risk of bricking the router and it becoming unusable. 

**Step 1: Router Comptability**

Before you even want to start to wondering if you could upgrade your router, first go to OpenWrt's table of compatible devices and see if the router you want to upgrade is there. If it isn't, I would recommend choosing a device that has documentation on the device page.  It will make your life easier especially if you’re new to this. I am using a Netgear R6080. Once you find the device, hover over the column labeled “device page” and click on in this case “R6080”.
https://openwrt.org/toh/start

<img width="1139" alt="Screenshot 2023-12-28 at 4 34 56 PM" src="https://github.com/CaptainIndy/Flashing-an-old-router-with-OpenWRT/assets/142528700/9c485477-16c3-458a-afc9-016c5ad67605">


**Step 2: Necessary Downloads**

This device page will show you the instructions on how to perform the firmware flash. 

 <img width="970" alt="Screenshot 2023-12-28 at 4 47 42 PM" src="https://github.com/CaptainIndy/Flashing-an-old-router-with-OpenWRT/assets/142528700/940bbacf-bc61-49eb-8545-b5c3ee7bcf8c">

Things we will need:
- NMRP Flash tool: A software used to send commands of packets to the router to tell it what firmware to use on boot or on start. This is what we are going to use to send the actual firmware file to our router when we start it up.

- Firmware snapshot: This will be under the installation table. The link is under the column titled “Firmware OpenWrt Install”. Download both the squash factory image and also the sysupgrade.bin in the column titled "Firmware OpenWrt Upgrade". Make sure to place both of these files in the same folder on your computer where you will remember the file path.

- OEM (Original Equipment Manufacturing) Firmware: In case you do not like the OpenWrt upgade and you want to rever back to the original version. The link for this download is in the third column in the installation table labeled "Firmware OEM Stock"
  - https://www.netgear.com/support/product/r6080
  - After clicking on that link, scroll down to "Firmware and Software Downloads" and click the arrow
  - Under "Current Versions", you will see a clickable labeled "Firmware version"... followed by the latest version, in 
    this case it is "1.0.0.54"
  - Click the arrow and hit the Download button. Make sure for consistency that this download is in the same file as the       firmware snapshots downloaded earlier.
 

**NMRP Flash**

When we click on the NMRP Flash link, https://github.com/jclehner/nmrpflash. It will take us to the github page, where we will be looking for the binaries. This will be different for windows and mac/linux os. In my case I am using a mac. 

We are going to scroll down to the "Readme" section and look at the second paragraph where it starts with “Prebuilt binaries”. There are two ways to do this: with or without Homebrew. I am going to be using Homebrew to do this. 

**Option 1: With Homebrew**
    - If you already have homebrew installed on your system, simply run the following command in your terminal: “brew            install nmrpflash”
    
**Option 2 Without Homebrew**
- If you do not want to use homebrew, simply click on the installation link.
  - https://github.com/jclehner/nmrpflash/releases. 
  - Click on the download file for your corresponding system. When it downloads, unzip the nmrp file, move to the              directory in your terminal and run the command “nrmp”, and it should begin the download.
    - You can check if it is installed by typing in “nmrp” and hitting enter and you should see options for nmrp                 command usages.

**Step 3: Flashing Preparation**

Before we flash our router, let's make sure everything is set up properly. When plugging in your router, you will need two ethernet cables. 

First, plug the router that you're upgrading into an outlet. Then take one of your ethernet cables and plug one end into the blue port labeled "internet". This is your WAN port. Connect the other end to any empty port (a LAN port) of a router that's already connected to the internet. 

Next, take your other ethernet cord and connect one end to any one of the open LAN ports labeled "1, 2, 3, 4" on the router you're upgrading. Take the other end of the cord and connect it to your computer. You will most likely need an Etherent cord adapter for your computer which you can buy off Amazon for $20.

Proceed by turn on your router to be upgraded by clicking the power button directly on your device. You should slowly start to see 4 green lights pop up. 

In your terminal, move to the folder in your downloads where you have the NMRP Flash firmware installed. From this point forward, if you installed through Homebrew, you do not need "./" when running the following commands. But if you did not then you will need it before running "nmrpflash"

From this folder in your terminal, run the command "nmrpflash -L" to determine which network interface is working with your Netgear router.
- For me, I will be choosing "en7" since that is the listed interface in the USB
- If it is not working, google the IP that is assigned to you using nmrpflash -L or ifconfig. Once you google the IP, login to your router with your information and then it is time to flash the router. 

**Step 4: Commence Flashing**
Before flashing, please read the instructions from this section in full. 

First power your router off manually by hitting the power button on your device. Then from the terminal, navigate to where your OpenWrt install firmware is located. Make sure that the Downloads are in there. We are looking for a squash img. Also have your network interface handy. 
- Firmware: openwrt-23.05.0-ramips-mt76x8-netgear_r6080-squashfs-factory.img
- Network interface: en7

Run the following command with required information (sudo privileges required):
- sudo nmrpflash -i en7 -f openwrt-23.05.0-ramips-mt76x8-netgear_r6080-squashfs-factory.img
- When you hit enter, the terminal will reply with "Waiting for Ethernet Connection...", and in return you will quickly turn your router back on manually on your device.
- 

<img width="703" alt="Screenshot 2023-12-28 at 6 24 23 PM" src="https://github.com/CaptainIndy/Flashing-an-old-router-with-OpenWRT/assets/142528700/ad05940d-4c56-4389-bf10-822b83b25c25">



**Step 5: Logging in**

**Step 6: Checking it works**

**Step 7: Issues I ran into**
  

