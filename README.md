# hackery-alpine-packages

*half cambodian hacker man*'s personal repository of Alpine Linux packages.

## Setting Up

1. Make sure you're a sudoer and in the abuild group:

```shell
$ sudo addgroup $USER wheel
$ sudo addgroup $USER abuild
```

2. Generate an abuild key and add it to the system's list of trusted keys:

```shell
$ abuild-keygen -a
$ sudo ln -s ~/.abuild/*.pub /etc/apk/keys/
```

3. Set up your `REPODEST` - You can use anywhere, but I use ~/.pkg

```shell
$ echo 'REPODEST="$HOME/.pkg"' >> $HOME/.abuild/abuild.conf
```

4. Add `.pkg/hackery-alpine-packages` to the system's list of APK repositories
```shell
$ echo "$HOME/.pkg/hackery-alpine-packages/" > /etc/apk/repositories
```

## Installing Packages

After going through the setup procedures, you can now build and install any package from `hackery-alpine-packages`. For example:

```shell
$ cd font-inter/
font-inter/ $ abuild
font-inter/ $ sudo apk add font-inter
```
