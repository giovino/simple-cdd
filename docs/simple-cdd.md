# Introduction

Example on how to use Simple-CDD to build a custom Debian 8.0.x ISO

## Prerequisites

1. Create a virtual machine with Debian 8.0.2 (Jesse)
1. Install simple-cdd

  ```bash
  $ sudo apt-get update && sudo apt-get install simple-cdd
  ```

## Use this repositories example simple-cdd configuration

1. Install git

  ```bash
  $sudo apt-get update && sudo apt-get install git
  ```
1. git clone Clone simple-cdd

  ```bash
  $ git clone https://github.com/giovino/simple-cdd.git
  ```
1. Build an iso

  ```bash
  cd simple-cdd/simple-cdd-01
  build-simple-cdd --conf ./simple-cdd-01.conf
  ```
1. Transfer the ISO image to your host machine

  ```bash
  scp simple-cdd:/home/<username>/simple-cdd/simple-cdd-01/images/debian-8.2-amd64-CD-1.iso .
  ```
1. Test the new ISO with your virtualization software

## Debian installer questions that require answers

1. Select a language
 * Language -> English

2. Select your location
 * Country, territory or area -> United states

3. Configure the keyboard
 * Keymap to use: -> American English
 
4. Configure the network
 * IP address -> 192.168.1.215
 * Netmask -> 255.255.255.0
 * Gateway -> 192.168.1.1
 * Name server addresses -> 192.168.1.1

5. Partition Disks
 * Write changes to disk -> Yes

6. Configure the package manager
 * Debian archive mirror country -> United States
 * Debian archive mirror -> ftp.us.debian.org
 * HTTP proxy information -> <blank>

7. Install grub boot loader on a hard disk
 * Device for boot loader installation -> /dev/sda

## System configuration post installation

1. User information
 * user: acme
 * password: acme corp preseed password
 * sudo privilegies: Yes
 
2. System Hostname
 * /etc/hostname is 'unassigned'
 
3. Remote access
 * OpenSSH Server installed and listening on port 22
 
## Resources

1. [Debian Handbook - 12.3.3. Simple-CDD: The All-In-One Solution](https://debian-handbook.info/browse/stable/sect.automated-installation.html)
1. [Debian Wiki - Simple-CDD Howto](https://wiki.debian.org/Simple-CDD/Howto)
1. [Silicone - Building a custom Debian CD](http://silicone.homelinux.org/2013/06/19/building-a-custom-debian-cd/)
1. [System automatic installation for Backup server](http://medspx.fr/projects/backup/preseed/)
1. [Github - thomlauret/apu.ath10k-debian](https://github.com/thomlauret/apu.ath10k-debian)
