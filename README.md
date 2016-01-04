# docker-armhf-motion

Set of scripts used to create a size optmized Docker image for the [Motion software package](http://www.lavrsen.dk/foswiki/bin/view/Motion/WebHome) for the ARM v7 architecture - specifically it has been tested on a [Odroid U3 board](http://www.hardkernel.com/main/products/prdt_info.php?g_code=g138745696275). The source code is taken from [this unofficial repository] (https://github.com/Mr-Dave/motion) on github.
The build of the software is performed inside a container and the resulting image is about 49MB in terms of size.
The following packages are built from sources:
* [libx264](http://git.videolan.org/?p=x264.git;a=summary)
* [ffmpeg](https://www.ffmpeg.org/) - the sources are taken from [here](https://github.com/FFmpeg/FFmpeg.git)
* [motion](http://www.lavrsen.dk/foswiki/bin/view/Motion/WebHome) - sources are taken from [here](https://github.com/Mr-Dave/motion.git)
Moreover the [dockerize tool](https://github.com/larsks/dockerize) it is used to build up the root file system of the resulting image.

 
