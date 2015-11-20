### Example on how to use Simple-CDD to build a custom Debian 8.0.x ISO

1. Create a virtual machine with Debian 8.0.2 (Jesse)
1. Install simple-cdd

  ```bash
  $ sudo apt-get update && sudo apt-get install simple-cdd
  ```
1. Browse through /usr/share/simple-cdd

  ```bash
  $ ls -l /usr/share/simple-cdd/
  $ less /usr/share/doc/simple-cdd/FAQ
  $ less /usr/share/doc/simple-cdd/README
  $ zless /usr/share/doc/simple-cdd/examples/simple-cdd.conf.detailed.gz
  ```
1. Create a working directory

  ```bash
  $ mkdir ~/simple-cdd-01
  $ cd ~/simple-cdd-01
  ```
1. Create a simple-cdd-01.conf file

  ```bash
  $ vim simple-cdd-01.conf
  ```
  add the following:
  ```bash
  # Configuration file for the simple-cdd-01 profile

  ## Profiles

  # Profiles to include on the CD
  profiles="simple-cdd-01"

  # To automatically select profiles (must also be listed in profiles):
  auto_profiles="simple-cdd-01"

  ## Distribution configuration
  profiles_udeb_dist="jesse"
  export CODENAME="jesse"
  dist="jesse"

  # Mirror configuration
  mirror_components="main contrib non-free"
  use_security_mirror="true"
  debian_mirror="http://ftp.us.debian.org/debian/"
  security_mirror="http://security.debian.org/"

  # Set to automatically boot after a timeout, in tenth's of a second.
  # i.e. for a 5 second timeout:
  BOOT_TIMEOUT=50

  # Set target architecture for build
  ARCH=amd64
  export ARCHES=$ARCH
  ```

1. Create a ```profiles``` directory

  ```bash
  $ mkdir profiles
  ```

1. Create a description file
  ```bash
  $ echo "Example simple-cdd iso creation" > profiles/simple-cdd-01.description
  ```

1. Create a Debian Preseed file
  ```bash
  $ vim profiles/simple-cdd-01.preseed
  ```
  add the following
  ```
  <to do>
  ```

1. Create a packages file

  In the packages file, list the package names (not libraries) of the packages you want to have installed on the system.

  ```bash
  $ vim profiles/simple-cdd-01.packages
  ```
  add the following:
  ```
  <to do>
  ```

1. Create a post-install script

  ```bash
  $ vim profiles/simple-cdd-01.postinst
  ```
  add the following:
  ```
  <to do>
  ```

1. Build an iso

  ```bash
  build-simple-cdd --conf simple-cdd-01.conf --force-preseed
  ```

Resources:

1. [Debian Handbook - 12.3.3. Simple-CDD: The All-In-One Solution](https://debian-handbook.info/browse/stable/sect.automated-installation.html)
1. [Debian Wiki - Simple-CDD Howto](https://wiki.debian.org/Simple-CDD/Howto)
1. [Silicone - Building a custom Debian CD](http://silicone.homelinux.org/2013/06/19/building-a-custom-debian-cd/)
1. [System automatic installation for Backup server](http://medspx.fr/projects/backup/preseed/)
1. [Github - thomlauret/apu.ath10k-debian](https://github.com/thomlauret/apu.ath10k-debian)
