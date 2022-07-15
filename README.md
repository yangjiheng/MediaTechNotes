# MediaTechNotes

## Table of Content
- **[Video Compression](#video_compression)**
    - **[Audio Encoding](#audio-encoding)**
    - **[Hardware Acceleration](#hardware-acceleration)**

## Video Compression
### Audio Encoding
* FFmpeg AAC encoding require a sample buffer size of 1024 (frame->nb_frame = 1024), otherwise, it will return "more samples than frame size" for avcodec_encode_audio2 function.

### Hardware Acceleration

* nVidia Jetson Hardware Acceleration Options (for Jetson Nano, Jetson Xavior). NV SDK ffnvcodec is not available. You can only get hardware acceleration with nvmpi through: <a href="https://github.com/jocover/jetson-ffmpeg">Jetson-FFMpeg</a>, (which by default works with FFmpeg 4.2, for other versions of FFmpeg, you need to apply patch manually). For other platforms, FFmpeg can support hardware acceleration directly through nvsdk.

# About This Repository

This repository is used to record media technology records as we march forward. It's not meant to be systematic, but more like random gems collected. Contact me if you want to connect with me:

* WeChat: jiheng_yang
* Discord: https://discord.gg/hgwZHpcK
* Email: jiheng.yang@gmail.com

