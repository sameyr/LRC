# Laptop to Single-Board Computer Connection 

This guide provides a step-by-step walkthrough for setting up remote access to your single-board computer. I'll use SSH (Secure Shell) to establish the connection between a laptop and a single-board computer.

## Pre-requisite

1. Single-Board Computer (This guide uses a Raspberry Pi 4)
2. Broadband Connection (Ensure both the laptop and the single-board computer are connected to the same network)
3. Remote Computer (A device from which you will access the single-board computer)

## Setup Instruction

1. Setting up Single Board Computer
    * Connect Raspberry Pi to the Power Source
    * Connect Raspberry Pi to your network/WiFi
  
2. Install SSh Server on the Single Board
    * Open Terminal on the Single Board
    * Update all the packages:
        
            sudo apt update
    * Install SSH Server

            sudo apt install openssh-server

    * Verify SSH is running
    
            sudo systemctl status ssh

    * if the service is not ruuning, start is with:

            susdo systemctl start ssh


3. Setting up Static Ip Address
    * This prevents the single-board computer from changing its IP address each time it connects to the network.
    * To set a static IP address, users can access the Network Settings by using the "nm-connection-editor" command.
    * A step-by-step guide for setting up a manual IP address can be found [here](staticIP.md).

4. 
