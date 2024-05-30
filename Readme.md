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

4. Set Up the Remote Laptop
   * Install an SSH Client
        * On Windows: Use PowerShell or install an SSH client like PuTTY.
        * On macOS/Linux: Use the terminal (SSH is pre-installed).
        * Connect to the Raspberry Pi via SSH

   * Open your SSH client.
   * Enter the SSH command using the static IP address of the Raspberry Pi:
       
                ssh username@192.168.1.100

   * Replace username with your Raspberry Pi username and 10.0.2.15 with the actual static IP address you set.
   * If this is your first time connecting, confirm the authenticity of the host by typing yes and pressing Enter.
   * Enter the password for the Raspberry Pi user when prompted.

## Verify Connection
   1. Check SSH Connection
   2. Once connected, you should have access to your single board computer terminal from your remote laptop.
   3. You can now execute commands on your single board as if you were directly connected to it.

## Check SSH Logs

If you encounter issues, check the SSH logs for errorsCheck SSH Logs:

        sudo journalctl -u ssh

