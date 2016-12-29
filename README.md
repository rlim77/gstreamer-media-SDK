

GStreamer-MSDK
==============
  GStreamer plugins for Intel(R) Media SDK


Overview
--------

GStreamer-MSDK consists of a collection of GStreamer plugins for
Intel(R) Media SDK.

  * 'mfxdecode' is used to decode H.264 AVC, MPEG-2, HEVC, VC-1, VP8 and
    JPEG videos using the underlying hardware capabilities. 

  * 'mfxsinkelement' is used to render the decoded frame to a Wayland / X11
    display.

  * 'mfxsink' is a bin element which contains mfxvpp and mfxsinkelement.

  * 'mfxvpp' is used to do video processing on decoded or RAW video frames.

  * 'mfxvc1parse' is used to parse VC-1 Simple, Main and Advance profiles.

  * 'mfxh264enc' is used to encode / transcode videos to H.264 format.
  
  * 'mfxhevcenc' is used to encode / transcode videos to H.265/HEVC format.

  * 'mfxmpeg2enc' is used to encode / transcode videos to MPEG-2 format.
  
  * 'mfxjpegenc' is used to encode / transcode videos to JPEG format.

License
-------

gstreamer-mediasdk libraries and plugin elements are available
under the terms of the GNU Lesser General Public License v2.1+


Features
--------

 - Decode H264 AVC, MPEG-2, JPEG, VC-1, HEVC, VP8 and VP9 Videos
 - Support rendering using Wayland
 - Support rendering using X11 with DRI3 backend
 - Support rendering using EGL
 - Support for headless decode pipelines (via fakesink)
 - Support all Media SDK postprocessing capabilities
 - Encode / transcode video into H.264, HEVC, MPEG-2 and JPEG formats.
 - Support VC-1 Simple, Main and Advance profile parsing.


Requirements
------------

Software requirements

  * MediaSDK 2017 MR1 for Yocto Embedded or
    Media Server Studio 2016 Professional R1 (Haswell / Broadwell)
  * GStreamer 1.6.x (up to including GStreamer 1.8):
  * GStreamer-Plugins-Base 1.6.x (up to including GStreamer 1.8):
  * libudev
  * libdrm
  * CMake
  
  * Renderers:
      Wayland (>=1.7)
      X11 (DRI 3)
      EGL

Hardware requirements

  * Intel Apollolake
  * Intel Braswell
  * Intel Haswell / Broadwell

Compiling
---------

GStreamer-MSDK uses the CMake build tool to build the plugins.
Create a build directory within the source directory and run the CMake
command to configure the build.

	mkdir build
	cd build
	cmake ..

To make a debug build:

	cmake .. -DDEBUG=ON
		

To build the plugins for Media Server Studio 2016 Linux Edition:

	cmake .. -DWITH_MSS_2016=ON
		

Only MediaSDK 2017 MR1 For Embedded supports VP9 decode. To disable VP9 decode
for other version of Media SDK:

	cmake .. -DMFX_VP9_DECODER=OFF


Next step is to compile the GStreamer-MSDK plugins:

	make

To install the plugins:

	make install

The plugins will be installed in the /usr/lib/gstreamer-1.0 directory.


Usage
-----

 - Please refer to README.example_usage for usage instructions.


Acknowledgements
----------------

This project is heavily based on the well-established GStreamer VAAPI architecture, hence we would like to publicly thank the GStreamer VAAPI developers for their hard work and contributions.

