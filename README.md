AirSonos
========

AirSonos is a server that adds Apple [AirPlay](https://www.apple.com/airplay/) (iOS, OS X) support to all Sonos devices on a network.

[Blog post for further reading (original post)](https://medium.com/@stephencwan/hacking-airplay-into-sonos-93a41a1fcfbb)


### Install

AirSonos requires [node.js](http://nodejs.org) >= v0.10.33 installed to run.

Install latest via source

```
$ git clone https://github.com/hectorgoan/airsonos-fixed
$ cd airsonos
$ npm install -g
```

### Run (macOS)

```
$ airsonos
```

Select device in sound properties

Enjoy!



### Platform Specific Instructions

Some non-OS X platforms require additional dependencies or steps to work.

- [Linux](#linux)
- [Synology](#synology)
- [Raspberry Pi](#raspberry-pi)
- [Windows](#windows)

#### Linux

On linux machines, there are dependencies for `libavahi-compat-libdnssd-dev libasound2-dev` packages (or equivalent). On distributions with `apt`...
```
$ sudo apt-get install libavahi-compat-libdnssd-dev libasound2-dev
```
for `yum`-based distros (CentOS/RHEL):
```
$ yum install avahi avahi-compat-libdns_sd avahi-compat-libdns_sd-devel
```

Note that for some distributions, `nodejs` must be [symlinked to `node` prior to install](https://github.com/stephen/airsonos/issues/90).

#### Synology

See: https://github.com/stephen/airsonos/issues/22

#### Raspberry Pi

You will likely need to [overclock your raspberry pi](https://github.com/stephen/airsonos/issues/42) to achieve acceptable performance. (Working on making this suck less.)

#### Windows

There is a pre-packaged Windows install that you can use.

- Ensure that 32-bit node.js ([version 0.10.33, 32-bit](http://nodejs.org/dist/v0.10.33/node-v0.10.33-x86.msi)) is installed.
- Download and Install the [Bonjour for Windows SDK](https://developer.apple.com/downloads/index.action?q=Bonjour%20SDK%20for%20Windows#) (requires an AppleID)
- Download [`airsonos_windows_x86.zip`](https://github.com/stephen/airsonos/releases/tag/0.0.19)
- Create the folder `C:\Users\username\AppData\Roaming\npm` if it doesn't already exist.
- Unzip the contents of this package at `C:\Users\username\AppData\Roaming\npm\`, so that `airsonos` and `airsonos.cmd` are directly inside the `\npm\` folder.
- Open a command prompt and type `where airsonos`. The output should look something like:
```
C:\Users\stephen>where airsonos
C:\Users\stephen\AppData\Roaming\npm\airsonos
C:\Users\stephen\AppData\Roaming\npm\airsonos.cmd
```
- Type `airsonos` to run.

Building from source on Windows is not recommended.

Please report issues for this pre-packaged Windows installer here: https://github.com/stephen/airsonos/issues/59

