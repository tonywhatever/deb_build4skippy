# deb_build4skippy

Preliminary:

Thanks to *Felix Fung* skippy-xd is not dead. The project's URL is: <https://github.com/felixfung/skippy-xd>/

Please note the following:

I am not an official debian-packager nor a coder and using Git is a pain in the neck for me. However I think that my very own two deb-pkgs are more up to date and far more debian-conforming in contrast to the available packages from the usual debian repos.

Goal:

My aim is to support Felix Fung's project with a proper debian-tree for the folks who want to create their own two debian binary packages to run skippy-xd.

Two installable unsigned *'Debian Bookworm (12)-amd64'* packages (skippy-xd_x.x.x-x_amd64.deb, skippy-xd-dbgsym_x.x.x-x_amd64.deb) are made available for downloading.

## Caveat

**Ubuntu** uses a different set of 'jpeg*' libraries. The below described recipe and the provided binaries **will not work for Ubuntu and Ubuntu-based distros**. I am sure it can be made to work with a few adjustments and tests but I personally won't do it (not enough hours in my day). Feel free to fork it.

.

## Where are the binary packages for downloading?

The container (holding 2 debs) by the name of **Debian12-skippy-xd_0.8.0-1_amd64_binaries.tar.gz** is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/1eNo3ZV5Gsh_oCZYq1oFlfgwwzaP1sArd/view?usp=sharing>

**Please check the integrity** of "Debian12-skippy-xd_0.8.0-1_amd64_binaries.tar.gz"

md5sums: eaed454fbb0ae56f2fa85e40746ec9f4

sha256sums: 6ce0ad7d6f08b569a50f445ae779e6a63330e5d56af0ac2edd0a6552d91682ee 

.



## How to create a skippy-xd debian package?

For Version 0.8.0 -- "Labyrinth" (19 June 2024) ~/felixfung

The following instruction are for **Debian 12 (Bookworm)** and **Devuan 5 (Daedalus)** and will also work for MX-Linux, Antix, SpiralLinux etc.

It does create the proper but unsigned Debian-Binaries-Packades only. We omit deliberatelly the creation of skippy-xd_x.x.x.orig.tar.gz (debianized source), skippy-xd_x.x.x-x.dsc and skippy-xd_x.x.x-x.debian.tar.xz.

### Befor anything else:

You need to update and upgrade the system first


### The required tools are:

```
sudo apt-get install build-essential dh-make fakeroot debhelper devscripts pkg-config
```

### The build-depends are:

```
sudo apt-get install libx11-dev libxft-dev libxcomposite-dev libxdamage-dev libxinerama-dev libgdcm-dev libjpeg62-turbo-dev libgif-dev
```

We don't use git, we download the zip-file!

### And now:

Download the zip-file from: <https://github.com/felixfung/skippy-xd> and unzip it, thus creating a directory 'skippy-xd-mster'.

Do not enter 'skippy-xd-master' but download the zip-file from <https://github.com/tonywhatever/deb_build4skippy> and unzip it.

Within the *newly* created directory 'deb_build4skippy-main' do:

```
cp -a /debian ../skippy-xd-master/
```

Now enter the skippy-xd-master directory. After checking if /debian is present and populated with files and a sub-directory execute the next command:

```
dpkg-buildpackage -rfakeroot -us -uc -b
```

and very shortly after you should find two new deb-binaries in the parent-directory of skippy-xd-master. (Any warning about debian/changelog can be safely ignored, it's OK)

You can now install them. Note that skippy-xd-dbgsym_x.x.x-x_amd64.deb is optional.
```
sudo gdebi skippy-xd_0.8.0-1_amd64.deb
```
```
sudo gdebi skippy-xd-dbgsym_0.8.0-1_amd64.deb

```

After the installation it will be listed using for example 'aptitude' under "Obsolete and Locally Created Packages".

It doesn't get much simpler to create your very own proper debian-package.



Enjoy!

