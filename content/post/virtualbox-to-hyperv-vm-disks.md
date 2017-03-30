+++
date = "2017-03-20T16:11:58+05:00"
draft = false
title = "Converting a VirtualBox VM Disk to be compatible with Hyper-V"
tags = [ "VirtualBox", "Hyper-V" ]
categories = [ "Virtualization" ]
+++

# Overview

This article covers converting an Oracle VirtualBox (VBox) Virtual Machine (VM) disk (or disks) to a format that Microsoft Hyper-V can understand and utilize.

Note: This article does not cover converting the VM’s actual configurations and corresponding settings; you will need to create a new Hyper-V VM to attach to the disk after conversion.

# Background

I originally had all my VMs running inside of VBox on Windows 10 Pro. I decided I wanted to install Docker for Windows to start learning and working with Docker. During that process, I was required to install the Windows Hyper-V role to host Hyper-V VMs. Once Hyper-V is installed and running, VBox pretty much becomes unusable and has very limited functionality, since Hyper-V has taken control of lots of native resources at this point to virtualize them.

My only option at this point was to convert my VBox VMs to Hyper-V equivalents; however, during this process, I found that one does not simply convert from a VDI to a VHD/VHDX. I also didn’t want to have to download, or sign-up to download, an application like StarWind’s V2V Converter (which works fantastic by the way, I just want this done the lightest way possible)

# Prerequisites
* Windows 10 Professional
* Hyper-V
* Oracle VM VirtualBox
* Existing VirtualBox VM
* Dariusz Stanislawek’s DS File Ops Kit
* Notepad++ or similar quality text editor
* Microsoft Virtual Machine Converter 3.0

# Exporting the VirtualBox VM as an Appliance

Your VBox VM’s disks are going to be stored as VDI files. This is a VBox format that is not native to the MS world and has some properties that are outside the bounds of even the VMDK format they’re supposedly based on (todo: find proof of this). This means that we need to get the VDI file into a format that’s easily portable to other platforms.

1.	Open the VBox Manager
2.	Click on File
3.	Click on Export Appliance... (CTRL+E)
4.	Select the Virtual Machine you wish to Convert
5.	Select a destination for the OVA file that will be generated
6.	Select OVF 2.0 for the Format
7.	Click Next
8.	Click Export

Directory does not exist for Export file

# Extract the VM’s Disks

The OVA file we just created is an archive of files that will contain a manifest with metadata about the exported VM, but more importantly, it contains the actual VM virtual disks that we need to convert to get our machines working over in Hyper-V.

1.	Go to the directory where you exported your OVA file
2.	Open the OVA file using your favorite archive program (I prefer 7-Zip myself)
3.	Extract the VMDK file(s) inside the archive

# Modify the Virtual Disk’s Descriptor

Each VMDK file exported from Virtual Box will contain a Disk Descriptor. This is metadata that explains to other applications, like Hyper-V, how the disk is setup and what it contains. There’s only one issue here that arises if we try to use the MS Virtual Box converter tools at this point.
Using dsfok to extract the Disk Descriptor

Open a 

# Sources and Reference

[How to Migrate VirtualBox VMs to Windows 10 Hyper-V](https://www.groovypost.com/howto/migrate-virtual-box-vms-windows-10-hyper-v/)

[Error when converting VmWare virtual disk to HyperV](http://stackoverflow.com/questions/37481737/error-when-converting-vmware-virtual-disk-to-hyperv/37482233#37482233)
