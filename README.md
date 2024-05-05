# deb_build4skippy

Preliminary:

Thanks to *Felix Fung* skippy-xd is not dead. The project's URL is: <https://github.com/felixfung/skippy-xd>/

Please note the following:

I am not a packager nor a coder and using Git is new to me. I like to think that my very own two preliminary deb-pkgs are presently (29-04-2024) more up to date and far more debian-conforming in contrast to the available packages from an official debian repo.

Goal:

My aim is to support Frlix Fung's project with a proper debian-tree for the folks who want to create their own two debian binary packages to run skippy-xd.

Two installable unsigned *'Debian Bookworm-amd64'* packages (skippy-xd_0.7.x-x_amd64.deb, skippy-xd-dbgsym_0.7.x-x_amd64.deb) are made available for downloading.

## Caveat

**Ubuntu**, as usual, had to use a different or just a renamed set of 'jpeg*' libraries. The below described recipe nor the provided binaries **will not work for Ubuntu and Ubuntu-based distros**. I am sure it can be made to work with a few adjustments and tests but I personally won't do it (not enough hours in my day). Feel free to fork it.


## How to create a skippy-xd debian package?

The following instruction are for **Debian 12 (Bookworm)** and **Devuan 5 (Daedalus)** and will also work for MX-Linux, Antix, SpiralLinux etc.


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

The container by the name of **Debian12-skippy-xd_0.7.2-1_amd64_binaries.zip** is on my 'Google Drive'. The link for downloding is: <https://drive.google.com/file/d/1aensbLkQwjdy3XlciQnHLkRguRV1e80n/view?usp=sharing>

Please check the integrity of the zip-file!

md5sums: 496cf7557660a0e664a85a3da0693130  Debian12-skippy-xd_0.7.2-1_amd64_binaries.zip

sha256sums: 2118d59beae045576d39557f01879e12e53457e3b754f4d5142045392ea991bb  Debian12-skippy-xd_0.7.2-1_amd64_binaries.zip


Enjoy!

