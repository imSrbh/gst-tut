
<p align="center">
  <img width="460" height="300" src="https://gstreamer.freedesktop.org/documentation/assets/images/gstreamer-logo.svg">
</p>

## GStreamer Plugins  
**GStreamer** is a framework for plugins, data flow, and media type handling/negotiation. It is used to create streaming media applications. Plugins are shared libraries that are dynamically loaded at runtime and can be extended and upgraded independently. When arranged and linked together, plugins form the processing pipeline that defines the data flow for a streaming media application.  

### "What is GStreamer?"  
In addition to the open source plugins you'll find in the GStreamer framework libraries, the DeepStream SDK includes NVIDIA hardware accelerated plugins that leverage GPU capabilities. For a complete list of DeepStream GStreamer plugins, see the NVIDIA DeepStream Plugin Manual.  
The following lists provide an overview of the open source and DeepStream plugins referenced in the exercises provided with this course.  
**Open source GStreamer plugins:**  
- **GstFileSrc** - Read data from a file: video data or images.  
- **GstH264Parse** - Parse the incoming H264 stream. For H265 codec, use H265Parse.  
- **GstRtpH264Pay** - Convert H264 encoded payload to RTP packets (RFC 3984).  
- **GstUDPSink** - Send UDP packets to the network. When paired with RTP payloader (GstRtpH264Pay) it can implement RTP streaming.  
- **GstCapsFilter** - Enforce limitations on data format without modifying data.  
- **GstV4l2Src** - Capture video from v4l2 devices.  
- **GstQTMux** - Merge streams (audio and video) into QuickTime(.mov) files.  
- **GstFileSink** - Write incoming data to a file in the local file system.  
- **GstURIDecodeBin** - Decode data from a URI into raw media. It selects a source element that can handle the given "uri" scheme and connects it to a decodebin.  


**NVIDIA Hardware Accelerated plugins:**  
- **Gst-nvstreammux** - Batch streams before sending for AI inference.  
- **Gst-nvinfer** - Run inference using TensorRT.  
- **Gst-nvvideo4linux2** - Decode video streams using the hardware accelerated decoder (NVDEC); Encode RAW data in I420 format to H264 or H265 output video stream using hardware accelerated encoder (NVENC).   
- **Gst-nvvideoconvert** - Perform video color format conversion. The first Gst-nvvideoconvert plugin before Gst-nvdsosd plugin converts stream data from I420 to RGBA and the second Gst-nvvideoconvert plugin after Gst-nvdsosd plugin converts data from RGBA to I420.  
- **Gst-nvdsosd** - Draw bounding boxes, text, and region of interest (ROI) polygons.  
- **Gst-nvtracker** - Track object between frames.  
- **Gst-nvmultistreamtiler** - Composite a 2D tile from batched buffers.  
- **Gst-nvv4l2decoder** - Decode a video stream.  
- **Gst-Nvv4l2h264enc** - Encode a video stream.  
- **Gst-NvArgusCameraSrc** - Provide options to control ISP properties using the Argus API.  




GStreamer is a powerful streaming media framework that supports modular and pipeline based workflows. It has a wide variety of plugin ecosystem. Using GStreamer pipelines we can create a complex streaming workflow.

Now that we have a high-level understanding of NVENC/NVDEC and GStreamer, let’s see how do we install and setup the SDK with GStreamer. GStreamer uses a meson and ninja build system for its builds.
 
