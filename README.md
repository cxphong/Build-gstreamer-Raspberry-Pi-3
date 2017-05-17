#Build

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

To link header & lib

```Shell
sudo nano /etc/ld.so.conf
```

Add

```Shell
include /usr/local/lib
```

Link 

```Shell
sudo ldconfig
```

# Replace 

## 1. Xoá version gstreamer hiện tại
	
```Shell
sudo rm -rf /usr/local/include/gstreamer-1.0
sudo rm -rf  /usr/include/gstreamer-1.0
sudo rm -rf /usr/local/lib/*
```

## 2. Copy 

```Shell	
sudo cp -r bin/* /usr/local/bin
sudo cp -r gstreamer-1.0 /usr/local/include
```

## 3. Build config (Same build above)

## 4. Checlk
	
```Shell
gst-launch-1.0 --version
```

