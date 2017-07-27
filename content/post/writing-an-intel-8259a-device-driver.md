+++
date = "2017-02-14T13:27:28+05:00"
draft = true
title = "Writing a Device Driver (kind-of) for an Intel 8259A PIC"

+++

# Background

I've recently been dabbling in the realm of building a custom operating system in C/C++, so that I can better understand what's happening under the hood when I'm writing code and troubleshooting issues that sit a-top more main-stream OSes. Part of this journey has led me to a requirement of configuring a Programmable Interrupt Controller to handle things like Keyboard input and communications with other peripherals down the road. Not having a very strong background in working with Integrated Circuits (ICs), but more-so a development background, I decided to document my adventures into working with an Intel 8259A PIC.

# Disclaimer

I mainly work in languages like C#, Java, and JavaScript. I'm still getting familiar with some of the newer concepts in recent releases of C/C++ and have not tried to optimize or implement any particular patterns in this article or its corresponding code. This is for reference and learning purposes only and would be written very differently if I were focused on writing something that's optimized and efficient on particular platforms. That said, please don't be an elitist ass-hat in the comments, but rather post constructive criticism and citations to help us all learn and improve our skillsets.

# Why the Intel 8259A PIC?

I happened to be using Oracle's VirtualBox as my Hyper Visor to test my operating system code, and it happens to emulate the Intel 8259A PIC. This was a very common PIC for x86 PCs and so I decided it was a great starting point to gain the knowledge and skills to work with other PICs down the road for things like IoT and other specialized devices. I will do another article down the road on Advanced PICs (APICs) since that's a newer iteration of this older model PIC, but why complicate things more at the start?

# Why is a PIC important?

Before PICs were in existence, we would have to perform a continuous "polling" methodology, and that load was put on the CPU. This meant that the CPU was wasting many cycles asking each device one-at-a-time…"Do you have anything I need to work on?" vs. actually running program instructions. Even if the device being polled didn't have anything to provide, the CPU still spent time asking anyway. With the rise of more peripherals being plugged into machines, this meant something needed to be done to help make better use of the CPU…The CPU should be running as many instructions as possible and not spending its day polling for no reason.

# What does a PIC look like?

PICs can come in many shapes and sizes. Some have more pins / wires available. It really depends on what the purpose of the equipment it's being placed in dictates.

# How do I configure a PIC?

