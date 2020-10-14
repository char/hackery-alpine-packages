# hackery-alpine-packages

*half cambodian hacker man*'s personal repository of Alpine Linux packages.

## Setting Up

```shell
$ sudo addgroup $USER wheel # Make sure you're a sudoer
$ sudo addgroup $USER abuild # Make sure you're in the abuild group
$ 
$ echo 'REPODEST="$HOME/.pkg"' >> $HOME/.abuild/abuild.conf # You can use any repo dest, but I use ~/.pkg
$ 
$ # Add your key to the system's APK repository 
$ abuild-keygen -a
$ sudo ln -s ~/.abuild/*.pub /etc/apk/keys/
$ 
$ # Add .pkg/hackery-alpine-packages to the system's APK lookup
$ echo "$HOME/.pkg/hackery-alpine-packages/" > /etc/apk/repositories
$ 
$ # You can now build and install any package from hackery-alpine-packages, e.g.:
$ cd font-inter/
font-inter/ $ abuild
font-inter/ $ sudo apk add font-inter
```
