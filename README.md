## 1. Uninstall default gstreamer 1.0

```bash
sudo apt-get remove gstreamer1.0
sudo apt-get remove gstreamer-1.0
```

## 2. Build

```bash
./gstreamer-build.sh
```
After building success:

Header is in /usr/local/inlude/gstreamer-1.0

Lib is in /usr/local/lib

## 3. Build config

To link header & lib when build your application

```xml
sudo vi /etc/ld.so.conf
```

Enter
/usr/local/lib


```bash
sudo ldconfig
```

