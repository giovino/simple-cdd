# Example on how to use Simple-CDD to build a custom Debian 8.0.x ISO

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

Resources:

1. [Debian Handbook - 12.3.3. Simple-CDD: The All-In-One Solution](https://debian-handbook.info/browse/stable/sect.automated-installation.html)
1. [Debian Wiki - Simple-CDD Howto](https://wiki.debian.org/Simple-CDD/Howto)
1. [Silicone - Building a custom Debian CD](http://silicone.homelinux.org/2013/06/19/building-a-custom-debian-cd/)
1. [System automatic installation for Backup server](http://medspx.fr/projects/backup/preseed/)
1. [Github - thomlauret/apu.ath10k-debian](https://github.com/thomlauret/apu.ath10k-debian)
