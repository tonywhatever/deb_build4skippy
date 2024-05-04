# deb_build4skippy

Preliminary:

Thanks to *Felix Fung* skippy-xd is not dead. The project's URL is: <https://github.com/felixfung/skippy-xd>/

Please note the following:

I am not a packager nor a coder and using Git is new to me. I like to think that my very own two preliminary deb-pkgs are presently (29-04-2024) more up to date and far more debian-conforming in contrast to the available packages from an official debian repo.

Goal:

My aim is to support Frlix Fung's project with a proper debian-tree for the folks who want to create their own two debian binary packages to run skippy-xd.

Two installable unsigned *'Debian Bookworm-amd64'* packages (skippy-xd_0.7.x-x_amd64.deb, skippy-xd-dbgsym_0.7.x-x_amd64.deb) will also be made available for downloading. At least that's the plan.

## How to create a skippy-xd debian package?

The following instruction are for **Debian 12 (Bookworm)** and **Devuan 5 (Daedalus)** and will also work for MX-Linux, Antix, SpiralLinux etc.

### Warning:

Unfortunately **Ubuntu**, as usual, had to use a different or just a renamed set of 'libjpeg*' libraries. The below described recipe **will not work for Ubuntu**. I guess it can be made to work fairly easy but I won't do it. Feel free to fork it.

### The required tools are:
```
sudo apt-get install build-essential dh-make fakeroot debhelper
```

### The build-depends are (git is optional):

```
sudo apt-get install git libx11-dev libxft-dev libxcomposite-dev libxdamage-dev libxinerama-dev libgdcm-dev libjpeg62-turbo-dev libgif-dev pkg-config
```

### And now:

Download the zip-file from: <https://github.com/felixfung/skippy-xd> and unzip it.

Within that new directory (skippy-xd-master do:
```
mv /DEBIAN  /DEBIAN.orig
cp Makefile Makefile.orig
```

Go back to the parent-directory and download the zip-file from <https://github.com/tonywhatever/deb_build4skippy> and unzip it.

Within the *newly* created directory do:

**Warning:** Replace /whatever/ with the actual path to skippy-xd-master!
```
cp -a /debian /whereever/skippy-xd-master/
cp Makefile_patched /whereever/skippy-xd-master/Makefile
cp Makefile_is_patched /whereever/skippy-xd-master/
```

Re-enter the skippy-xd-master directory again. After checking if /debian, Makefile and Makefile_is_patched is present execute the next command:
```
dpkg-buildpackage -rfakeroot -us -uc -b
```

and very shortly after you should find two new deb-files in the parent-directory of skippy-xd-master.

You can now install them. Note that skippy-xd-dbgsym_0.7.x-x_amd64.deb is optional)
```
sudo gdebi skippy-xd_0.7.x-x_amd64.deb
sudo gdebi skippy-xd-dbgsym_0.7.x-x_amd64.deb
```

It doesn't get much simpler to create your very own proper debian-package.


## Where are the binary packages for downloading?

Still on my computer! Sorry.

Enjoy!

