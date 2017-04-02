# docker-armhf-motion

Set of scripts used to create a size optmized Docker image for the [Motion software package](http://www.lavrsen.dk/foswiki/bin/view/Motion/WebHome) for the ARM v7 architecture - specifically it has been tested on a [Odroid U3 board](http://www.hardkernel.com/main/products/prdt_info.php?g_code=g138745696275). The source code is taken from [this unofficial repository] (https://github.com/Mr-Dave/motion) on github.
The build of the software is performed inside a container and the resulting image is about 49MB in terms of size.
The following packages are built from sources:
* [libx264](http://git.videolan.org/?p=x264.git;a=summary)
* [ffmpeg](https://www.ffmpeg.org/) - the sources are taken from [here](https://github.com/FFmpeg/FFmpeg.git)
* [motion](http://www.lavrsen.dk/foswiki/bin/view/Motion/WebHome) - sources are taken from [here](https://github.com/Mr-Dave/motion.git)

Moreover the [dockerize tool](https://github.com/larsks/dockerize) it is used to build up the root file system of the resulting image.
The final result is a Docker image containing the file system represented by this tree:
```
.
|-- [-rw-r--r--]  Dockerfile
|-- [drwxr-xr-x]  etc
|   |-- [-rw-r--r--]  group
|   |-- [-rw-r--r--]  nsswitch.conf
|   `-- [-rw-r--r--]  passwd
|-- [-rw-r--r--]  image-tree.txt
|-- [drwxr-xr-x]  lib
|   |-- [drwxr-xr-x]  arm-linux-gnueabihf
|   |   |-- [-rwxr-xr-x]  libc.so.6
|   |   |-- [-rw-r--r--]  libdl.so.2
|   |   |-- [-rw-r--r--]  libm.so.6
|   |   |-- [-rw-r--r--]  libnss_compat.so.2
|   |   |-- [-rw-r--r--]  libnss_dns.so.2
|   |   |-- [-rw-r--r--]  libnss_files.so.2
|   |   |-- [-rwxr-xr-x]  libpthread.so.0
|   |   `-- [-rw-r--r--]  libz.so.1
|   `-- [-rwxr-xr-x]  ld-linux-armhf.so.3
`-- [drwxr-xr-x]  usr
    |-- [drwxr-xr-x]  bin
    |   |-- [-rwxr-xr-x]  ffmpeg
    |   |-- [-rwxr-xr-x]  ffprobe
    |   |-- [-rwxr-xr-x]  ffserver
    |   `-- [-rwxr-xr-x]  motion
    `-- [drwxr-xr-x]  lib
        |-- [drwxr-xr-x]  arm-linux-gnueabihf
        |   `-- [-rw-r--r--]  libjpeg.so.8
        `-- [-rwxr-xr-x]  libx264.so.148

7 directories, 20 files
```

 
