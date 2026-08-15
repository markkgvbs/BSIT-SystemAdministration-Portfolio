# Enterprise Server Deployment and Operating System Installation

**Course:** ITEP 414 - System Administration and Maintenance
**Week:** 3 Portfolio Project
**Student:** Mark Give V. De Leon
**Program:** BSIT 3C

## Project Overview

This project covers the full deployment of an enterprise Linux server using Ubuntu Server. The activity simulates the role of a Junior System Administrator setting up a new server for a startup company, ABC Startup Solutions. The server was installed, configured, secured, and documented following standard enterprise practices. The project also includes a comparison of boot technologies (BIOS vs UEFI) and a comparison of server operating systems (Windows Server, Ubuntu Server, and Rocky Linux).

## Learning Objectives

- Explain the purpose of an operating system in enterprise environments
- Differentiate BIOS and UEFI firmware
- Explain the stages of the computer boot process
- Compare Ubuntu Server, Windows Server, and Rocky Linux
- Install Ubuntu Server in a virtual machine
- Configure server settings during installation
- Enable secure remote administration using SSH
- Verify server functionality
- Document installation procedures

## Virtual Machine Specifications

| Component | Specification |
|---|---|
| Name | Ubuntu-Server-Week03 |
| RAM | 4 GB |
| CPU | 2 Virtual Processors |
| Storage | 40 GB (VDI) |
| Network | NAT |
| Optical Drive | Ubuntu Server 26.04 LTS ISO |

## Installation Summary

Ubuntu Server was installed using the guided installation wizard. The language was set to English, keyboard layout to English (US), and the hostname was configured as `server01`. Network configuration was assigned automatically through DHCP, receiving the IP address `10.0.2.15`. The disk was partitioned using the guided "Use Entire Disk" option with an LVM volume group, formatted as ext4, with a 2 GB `/boot` partition and the remaining space allocated to the root partition. OpenSSH Server was installed during setup to enable secure remote access. No additional server snaps were installed.

## Configuration Summary

- Hostname: `server01`
- Filesystem: ext4
- Disk size: 40 GB
- Partition scheme: Guided LVM (boot partition + LVM volume group)
- SSH: Installed and enabled during setup
- Password authentication over SSH: Enabled

## Verification Results

| Task | Command | Result |
|---|---|---|
| Login | N/A | Successful login with created user account |
| Hostname check | `hostname` | Returned `server01` |
| IP address check | `ip addr` | Confirmed IP `10.0.2.15` |
| Internet connectivity | `ping -c 4 google.com` | 4 successful replies, 0% packet loss |
| System update | `sudo apt update && sudo apt upgrade -y` | Packages updated successfully |
| SSH service check | `systemctl status ssh` | Status: active (running) |

## BIOS vs UEFI Highlights

UEFI has largely replaced BIOS in modern computers due to faster boot times, support for disks larger than 2 TB, a graphical setup interface, and built-in security through Secure Boot. BIOS is limited to a 2 TB disk size, uses the older Master Boot Record partition style, and has no built-in security checks during boot. The full comparison table and explanation are available in `BIOS_vs_UEFI.pdf`.

## Boot Process Flowchart

The Ubuntu Server boot process follows these stages: Power On, BIOS/UEFI Initialization, Boot Device Detection, Boot Loader (GRUB), Linux Kernel Loads, init/systemd Starts, Services Start, and Login Prompt. The full flowchart is available in `BootProcessFlowchart.pdf` and inside the `diagrams/` folder.

## Challenges Encountered

During the Ubuntu Server installation, the virtual machine crashed unexpectedly after the user profile setup screen, requiring a fresh restart of the installation process. During the system update step, one package (`linux-firmware-amd-misc`) failed to download from the regional Ubuntu mirror due to a 403 error. This was resolved by switching to the global Ubuntu archive mirror, and the package was confirmed to be non-essential for the virtual machine environment.

## Reflection

This Week 3 activity gave me my first real hands on experience setting up a server from scratch, and it taught me a lot more than I expected going in. Before this project, I had never worked with Ubuntu Server, only Ubuntu Desktop a little, so seeing a plain black terminal screen with no graphical interface was strange at first. I later understood that this is actually how real servers are supposed to run, since companies do not need a desktop interface taking up resources on a machine that is meant to run services in the background.

The installer navigation was one of the more challenging parts for me. At one point during the setup, right after entering my password on the user profile screen, the virtual machine suddenly crashed and I had to restart the whole installation process from the beginning. It was frustrating at first, but it taught me that these kinds of issues are normal in system administration work, and that patience and being willing to just try again is part of the job. I also had to learn how to properly move through each installer screen using Tab instead of arrow keys, which I did not expect to be an issue at first.

Understanding the Linux commands was also new for me. Running commands like hostname, ip addr, and systemctl status ssh for the first time felt intimidating, but once I saw the output and understood what each command was actually checking, it started to make more sense. I also ran into a small issue during the system update where one package failed to download from the regional mirror, and I learned how to switch to a different mirror source to fix it instead of just giving up on the update.

Beyond the technical steps, this activity helped me understand why operating system choice and boot technology actually matter in real environments. Comparing BIOS and UEFI showed me how much boot technology has changed over the years, especially with things like Secure Boot and support for larger drives. Comparing Windows Server, Ubuntu Server, and Rocky Linux also helped me realize that there is no single best operating system, it really depends on what a company already uses and what they need the server to do.

Overall, this project pushed me to slow down, read instructions carefully, and troubleshoot problems on my own instead of expecting everything to work perfectly on the first try. These are skills I know I will need moving forward, especially since my goal is to become a full stack developer who understands not just how to build applications, but also how the systems running them actually work underneath.

## References

- Ubuntu Server official documentation: https://ubuntu.com/server/docs
- Canonical, Ubuntu 26.04 LTS Release Notes
- Microsoft Windows Server 2025 Evaluation Center
