# Flashing-an-old-router-with-OpenWRT
**Overview**

OpenWrt is an open source software firmware. Flashing your router allows for enhanced security and additional upgrades from the Openwrt community.

Disclaimer: by using OpenWrt on an router voids any existing warranty on the router itself. There is also a risk of bricking the router and it becoming unusable. 

**Step 1: Router Comptability**

Before you even want to start to wondering if you could upgrade your router, first go to OpenWrt's table of compatible devices and see if the router you want to upgrade is there. If it isn't, I would recommend choosing a device that has documentation on the device page.  It will make your life easier especially if you’re new to this. I am using a Netgear R6080.

Once you find the device, hover over the column labeled “device page” and click on in this case “R6080”.
https://openwrt.org/toh/start

<img width="1139" alt="Screenshot 2023-12-28 at 4 34 56 PM" src="https://github.com/CaptainIndy/Flashing-an-old-router-with-OpenWRT/assets/142528700/9c485477-16c3-458a-afc9-016c5ad67605">


**Step 2: Necessary Downloads**

This device page will show you the instructions on how to perform the firmware flash. 
Things we will need:
- NMRP Flash tool: A software used to send commands of packets to the router to tell it what firmware to use on boot or on start. This is what we are going to use to send the actual firmware file to our router when we start it up.

- Firmware snapshot: This will be under the installation table. The link is under the column titled “Firmware OpenWrt Install”. Download both the squash factory image and also the sysupgrade.bin in the column titled "Firmware OpenWrt Upgrade". Make sure to place both of these files in the same folder on your computer where you will remember the file path.
  <img width="970" alt="Screenshot 2023-12-28 at 4 47 42 PM" src="https://github.com/CaptainIndy/Flashing-an-old-router-with-OpenWRT/assets/142528700/940bbacf-bc61-49eb-8545-b5c3ee7bcf8c">

  **NMRP Flash**
      When we click on the NMRP Flash link, https://github.com/jclehner/nmrpflash. It will take us to the github page and on this github page we are going to be looking for binaries. This will be different for windows and mac/linux os. In my case I am using a mac. 
We are going to scroll down to the readme section and look at the second paragraph where it starts with “Prebuilt binaries”. There are two ways to do this: with or without Homebrew. I am going to be using Homebrew to do this. 
  **Option 1: Homebrew**
    - If you already have homebrew installed on your system, simply run the following command in your terminal: “brew install nmrpflash”
  **Option 2: 
    If you do not want to use homebrew, simply click on the installation link.
  https://github.com/jclehner/nmrpflash/releases. Click on the download file for your             corresponding system. I am using MacOS. When it downloads, unzip the nmrp file, move to the     directory in your terminal and run “nrmp” and it should begin the download.
  You can check if it is installed by typing in “nmrp” and hitting enter and you should see       options for nmrp command usages. 
  

