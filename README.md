The default Gstreamer version on Raspberry Pi 3 is 1.4.4. 

This is guide to build gstreamer from scratch. Building takes more 1h.

Btw, I already built some version, so you can extract it to use.

# Note

From gst-plugin-bad v1.3.1, *glimagesink* replaces *eglglessink*, and *glimagesink* does not automatically scale video to fit screen

# Build from scratch

## 1. Uninstall default gstreamer 1.0

```Shell
sudo apt-get remove gstreamer1.0
sudo apt-get remove gstreamer-1.0
```

## 2. Build

```Shell
chmod +x gstreamer-build.sh
./gstreamer-build.sh
```
After building success:

Header is in /usr/local/inlude/gstreamer-1.0 

Lib is in /usr/local/lib

## 3. Config

### Copy header

```Shell
sudo cp -r /usr/local/include/gstreamer-1.0 /usr/include/
```

**Note:**

In some version *gstconfig.h* is not in */usr/local/include/gstreamer-1.0/gst/* but in */usr/local/lib/gstreamer-1.0/include/gst*.

Must copy it to */usr/include/gstreamer-1.0/gst/*

### To link lib

```Shell
sudo nano /etc/ld.so.conf
```

### Add

```Shell
include /usr/local/lib
```

### Link 

```Shell
sudo ldconfig
```

# Using prebuilt 

## 1. Delete old build
	
```Shell
sudo rm -rf /usr/local/include/gstreamer-1.0
sudo rm -rf  /usr/include/gstreamer-1.0

# Remove only gstreamer, in my case it has only gstreamer lib
sudo rm -rf /usr/local/lib/*
```

## 2. Extract version you want & copy into file system

```Shell	
sudo cp -r bin/* /usr/local/bin
sudo cp -r gstreamer-1.0 /usr/local/include
sudo cp -r lib/* /usr/local/lib
```

## 3. Build config (Same build above, if not)

## 4. Check
	
```Shell
gst-launch-1.0 --version
```

