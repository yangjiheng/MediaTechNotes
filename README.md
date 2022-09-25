# MediaTechNotes

## Table of Content
- **[Video Compression](#video-compression)**
    - **[Audio Encoding](#audio-encoding)**
    - **[Remuxing](#remuxing)**
    - **[Hardware Acceleration](#hardware-acceleration)**
    - **[FFmpeg Gists](#ffmpeg-gists)**

## Media Compression
### Audio Encoding
* FFmpeg AAC encoding require number of samples each frame be exactly 1024 (frame->nb_samples = 1024), otherwise, it will return "more samples than frame size" for avcodec_encode_audio2 function (error code -22, Invalid Argument).
* When creating AVFrame with PCM buffer using avcodec_fill_audio_frame, be sure to read the document clearly:
    > The buffer buf must be a preallocated buffer with a size big enough to contain the specified samples amount. The filled AVFrame data pointers will point to this buffer.

    So buf pointer needs to be pre-allocated and will be assigned to AVFrame. Therefore, don't try to reuse the pointer for other things, which will cause electronic noise after the AVFrame done processing (dirty buffer).

### Remuxing
* By far, the best description of remuxing implementation can be found at: https://www.bookstack.cn/read/ffmpeg-libav-tutorial/spilt.3.spilt.4.blank, for all those years, it still works like a charm by following the steps.

### FFmpeg Gists
* Generating a new AVPacket can be done in three ways, described in : https://www.anycodings.com/1questions/321931/create-a-copy-of-an-avpacket-structure

### Hardware Acceleration

* nVidia Jetson Hardware Acceleration Options (for Jetson Nano, Jetson Xavior). NV SDK ffnvcodec is not available. You can only get hardware acceleration with nvmpi through: <a href="https://github.com/jocover/jetson-ffmpeg">Jetson-FFMpeg</a>, (which by default works with FFmpeg 4.2, for other versions of FFmpeg, you need to apply patch manually). For other platforms, FFmpeg can support hardware acceleration directly through nvsdk.

# About This Repository

This repository is used to record media technology records as we march forward. It's not meant to be systematic, but more like random gems collected. Contact me if you want to connect with me:

* WeChat: jiheng_yang
* Discord: https://discord.gg/hgwZHpcK
* Email: jiheng.yang@gmail.com

