> The apt-cache command line tool is used for searching apt software package cache. In simple words, this tool is used to search software packages, collects information of packages and also used to search for what available packages are ready for installation

> To find out the package name and with it description before installing :
```
# apt-cache search vsftpd
vsftpd - lightweight, efficient FTP server written for security
vsftpd-dbg - lightweight, efficient FTP server written for security (debug)
ccze - A robust, modular log coloriser
ftpd - File Transfer Protocol (FTP) server
yasat - simple stupid audit tool
```

>  To find and list down all the packages :
```
# apt-cache pkgnames vsftpd
vsftpd
vsftpd-dbg
```

> To check information of package along with it short description say (version number, check sums, size, installed size, category etc)

```
# apt-cache show vsftpd
Package: vsftpd
Priority: extra
Section: net
Installed-Size: 328
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
Original-Maintainer: Jörg Frings-Fürst <debian@jff-webhosting.net>
Architecture: amd64
Version: 3.0.3-3ubuntu2
Replaces: ftp-server
Provides: ftp-server
Depends: debconf (>= 0.5) | debconf-2.0, init-system-helpers (>= 1.18~), libc6 (>= 2.15), libcap2 (>= 1:2.10), libpam0g (>= 0.99.7.1), libssl1.0.0 (>= 1.0.0), libwrap0 (>= 7.6-4~), adduser, libpam-modules, netbase
Recommends: logrotate, ssl-cert
Conflicts: ftp-server
Filename: pool/main/v/vsftpd/vsftpd_3.0.3-3ubuntu2_amd64.deb
Size: 115492
MD5sum: c0c62c32c75eea6a4d36e91b8695453b
SHA1: b97efcd25ed49537f0601b3687f39b07e126c0c0
SHA256: c1d07ecf1e8fd72714f0cc803498a59c9b6a88168ed340e9560e7e904d6bfc18
Description-en: lightweight, efficient FTP server written for security
 This package provides the "Very Secure FTP Daemon", written from
 the ground up with security in mind.
 .
 It supports both anonymous and non-anonymous FTP access, PAM authentication,
 bandwidth limiting, and the Linux sendfile() facility.
Description-md5: 81386f72ac91a5ea48f8db0b023f3f9b
Homepage: http://vsftpd.beasts.org/
Bugs: https://bugs.launchpad.net/ubuntu/+filebug
Origin: Ubuntu
Supported: 5y
```

> The apt-get command is probably the most often used member of the apt suite of packaging tools. Its main purpose is interfacing with remote repositories maintained by the distribution’s packaging team and performing actions on the available packages.

> The ‘update‘ command is used to resynchronize the package index files from the their sources specified in /etc/apt/sources.list file. The update command fetched the packages from their locations and update the packages to newer version.

```
apt-get update
```

> The ‘upgrade‘ command is used to upgrade all the currently installed software packages on the system. Under any circumstances currently installed packages are not removed or packages which are not already installed neither retrieved and installed to satisfy upgrade dependencies.

```
apt-get upgrade
```

> The procedure to update a a specific package ( for eg :- ngnix ) on Ubuntu :

```
Fetch package index by running sudo apt update command

apt-get update

apt-get install nginx

If nginx package is already installed it will try to update to latest version
```

>  The following will not install a new nginx package if not installed:

```
apt-get --only-upgrade install nginx
```

> Perform a Dry Run of Package Actions

```
apt-get install -s vsftpd
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libatkmm-1.6-1v5 libcairomm-1.0-1v5 libglibmm-2.4-1v5 libgtkmm-3.0-1v5 libgtkspell3-3-0 libpangomm-1.4-1v5 libsigc++-2.0-0v5
Use 'apt autoremove' to remove them.
The following NEW packages will be installed:
  vsftpd
0 upgraded, 1 newly installed, 0 to remove and 17 not upgraded.
Inst vsftpd (3.0.3-3ubuntu2 Ubuntu:16.04/xenial [amd64])
Conf vsftpd (3.0.3-3ubuntu2 Ubuntu:16.04/xenial [amd64])
```
