Dual boot ubuntu 16.04 LTS with Windows 10 on MSI GS63VR 7RF 

-- Install Ubuntu from USB

Download Ubuntu 16.04 LTS image (http://releases.ubuntu.com/16.04.3/ubuntu-16.04.3-desktop-amd64.iso)

Make Bootable USB (https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-macos#0)

Go into BIOS using del key
Disable secure boot

Install Ubuntu 16. from USB
Go into BIOS using del key
In the UEFI boot order select ubuntu so that GRUB will be loaded first

-- Fix login loop (only background and mouse cursor after login)

Boot using "Advance Setting for Ubuntu" (from the GRUB menu)
![GRUB](https://i.imgur.com/CbvJyyI.jpg)
Disable graphic card using "failsafeX"
Resume normal boot usinge "resume"
![Resume](https://i.imgur.com/K3qpfqG.png)


Open terminal install latest Nvidia Driver

		sudo apt-get install --reinstall ca-certificates
		sudo apt-get update
		sudo apt purge 'nvidia.*'
		sudo add-apt-repository ppa:graphics-drivers/ppa
		sudo apt update
		sudo apt-get install nvidia-375
		reboot

-- install CUDA 8.0

		sudo apt update
		sudo apt-get install cuda-8-0

-- Install msiklm to control keyboard lights

		git clone https://github.com/Gibtnix/MSIKLM.git
		cd MSIKLM/
		sudo msiklm 0x9500ff