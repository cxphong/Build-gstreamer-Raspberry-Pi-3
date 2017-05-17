1. gst-plugin-bad

  ```
    /root/src/gstreamer/gst-plugins-bad/gst-libs/gst/gl/gstglapi.h:41:21: fatal error: EGL/egl.h: No such file or directory
   #include <EGL/egl.h>
  ```
 Just build gst-plugin-bad again
 
 2. gst-omx
 
  ```
   make[3]: Entering directory '/root/src/gstreamer/gst-omx/examples/egl'
    CC       testegl-testegl.o
    CCLD     testegl
  /usr/bin/ld: testegl-testegl.o: undefined reference to symbol 'glUniformMatrix4fv'
  //opt/vc/lib/libGLESv2.so: error adding symbols: DSO missing from command line
  ```

Try **ldconfig** and build only gst-omx again
