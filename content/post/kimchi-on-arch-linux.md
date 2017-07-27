+++
date = "2017-05-09T08:03:34+05:00"
draft = true
title = "Getting Kimchi running on Arch Linux"
tags = [ "libvirt", "linux", "kvm", "webui" ]
categories = [ "Virtualization" ]
+++

# Getting Kimchi running on Arch Linux

## Overview

I recently started configuring an Arch Linux server with KVM for proper virtualization with QEMU. When I got to the point of being ready to provision Domains (Virtual Machines), it became a real pain to build-out the XML files for the machine defintiions. After some quick searching, I came across Kimchi which aims to provide a simply web UI, capable of provisioning simple configurations for KVM through libvirt.

Throughout my journey installing and configuring it, I encountered a few issues installing it on Arch Linux, but was able to overcome those issues and get everything running. This article will share the entire process of installing and configuring Kimchi on Arch Linux.

## Prerequisites

This article assumes that you have the following:

* A machine already configured and running Arch Linux and KVM
* General knowledge of KVM and its capabilities
* General knowledge of Arch Linux and what the AUR is
* Understanding of what [Kimchi](https://github.com/kimchi-project/kimchi) is

## Kimchi exists in the AUR

Kimchi is not available as a baseline (wording?) package from Arch Linux. It is, however, existant in a package provided by maintainers in the Arch Linux AUR. This means that there will be a few additional steps to acquiring and installing Kimchi on Arch.

## Configuring Arch to pull from the AUR


mkdir ~/builds
