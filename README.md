#Build

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

```text
/usr/local/lib
```

Link 

```bash
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

