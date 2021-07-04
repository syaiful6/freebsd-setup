FreeBSD provides binary compability with Linux, allowing users to run most
Linux binaries.

### Configure

```
kldload linux
```

For 64-bit compability

```
kldload linux64
```

At this rate, you need to install `emulators/linux_base-c7` or simply `emulators/linux-c7`.

Then enable Linux compability tool at boot time:

```
linux_enable="YES"
```

#### Linux binary can't send request because of SSL error

Fix it by link BSD ca-root to linux's:

```
ln -s /usr/local/share/certs/ca-root-nss.crt /compat/linux/etc/pki/tls/certs/ca-bundle.crt
```
