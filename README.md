# Virtual_LaTex
Makes a virtual machine with a LaTex compiler to use with Visual Studio Code's remote host plugin

## Introduction

Shalom. This repository is made for users who want to stop using overleaf to write up lengthy LaTex reports/notes yet don't want to go through the hassel of setting everything up on a local machine / pollute your environment. This repo will allow for complete isolation of all things latex related from your computer via the use of _Virtualization_. Once everything is installed and runing, compiling LaTex documents will be as simple as hitting CTRL+S. Additionally, this will allow you to view your PDF document on the side exactly like overleaf, but it will be faster, look better, and all happen locally(No internet required).

## Requirements

Before installation can begin, you will need a few things:

1. [Visual Studio Code](https://code.visualstudio.com)
    * With the `Remote-SSH` plugin

2. [Vagrant](https://www.vagrantup.com)

3. [Virtual Box](https://www.virtualbox.org)

4. Putty

Visual studio is the text editor we will use to connect to the vm with the LaTex compiler and edit .tex files  
Vagrant is the vm configuartion tool we will use to install all of the necessary packages and set up the box  
Virutal Box is the vm hypervisor Vagrant will use to bring up a base VM (more specifially a ubuntu box).

## Installation

Installation is a simple as running the install script... if you're on mac or linux.  
For winows users here is what you will need to do:  
1. make a new folder called `shared_folder`. **Make sure the spelling is exact**
2. Add whatever .tex files you wish to edit/compile into the shared_folder
3. In a command prompt, enter the folder where this file exits using the command: 
    * `cd <path_of_this_file>` 
4. In the same cmd prompt, type in the following command:  
    * `vagrant up`
5. Get comfy, this might take a while.

Thats it! Once the cmd prompt returns, you are ready for the next step: Connecting VScode to the new vm.

## Setting Up VS Code

Congradulatons! if you've made it this far, then you have successfully make a whole new linux environment right onto your personal computer. Now we need to Set up a connection for you VS code to interact with said VM. For starter open up a CMD prompt and type in `vagrant ssh-config`. Take the following output and copy it. Paste the output into the ssh/config file which is located at: `c: \Program Files\Git\etc\ssh\config`. From There all you need to do is open VS code, click the blue box in the bottom left corner, select `Remote-SSH: Connect to Host`, and then select default.  

Once final step here is to install the `LaTex Workshop` plugin on the VS code window which is connected to the VM.

## Compiling LaTex Files

Once your VS code is open and connected to the VM, simply open the .tex file and click the little button with the blue magnifying glass. Bam, a PDF of your current LaTex should show up right next to your code. 

