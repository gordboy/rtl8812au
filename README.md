# rtl8812au

## Realtek 8812AU driver version 5.2.20

Only supports 8812AU chipset. 

Works fine with 4.13 kernel. Source now builds with no warnings or errors.

Added (cosmeticly edited) original Realtek_Changelog.txt, this README.md and dkms.conf.

### Building

To build and install module manually:
```sh
$ make
$ sudo make install
```

To use dkms install:

```sh
  (as root, or sudo) copy source folder contents to /usr/src/rtl8812au-5.2.20
```

```sh
$ sudo dkms add -m rtl8812au -v 5.2.20
$ sudo dkms build -m rtl8812au -v 5.2.20
$ sudo dkms install -m rtl8812au -v 5.2.20 
```

To use dkms uninstall and remove:

```sh
$ sudo dkms remove -m rtl8812au -v 5.2.20 --all
```

### NetworkManager

As others have noted, people using NetworkManager need to add this stanza to /etc/NetworkManager/NetworkManager.conf

```sh
  [device]
  wifi.scan-rand-mac-address=no
```
