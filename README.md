# Building Docker Image for NVIDIA Deepstream and Install Application 

The Purpose of this repository is to create a Deepstream/Triton-Server streamlined infrastructure for running an application that utilizes YOLOv7 models to perform inference on video files or RTSP streams. It then showcases the output on an RTSP URL, providing a straightforward demonstration of end-to-end AI processing.**

This repo also provides a set of instructions for building a Docker image tailored for deploying a Deepstream application with support for YOLOv7 model inference served by Triton Server. It outlines the steps required to set up the environment and install necessary dependencies.
 

### 1. Deploy and Start Triton Server

Follow the steps on below link to Start Triton Server<br>
[Triton Server - YOLOV7.](https://github.com/levipereira/docker_images/triton-server-yolov7)


### 2. Deploy and Start Deepstream 
Follow the steps on below link to Start Deepstream<br>
[Deepstream - YOLOV7.](https://github.com/levipereira/docker_images/deepstream-yolov7)



## 4. Using Sample Application `deepstream-yolov7-triton-server-rtsp-out`  

To use this sample application, follow the steps below from within the container:

The sample application is installed on `/deepstream_python_apps/apps/deepstream-yolov7-triton-server-rtsp-out/`

This sample application supports input streaming from both `file://` and `rtsp://` sources. It processes the input and streams the output via RTSP at the following URL: `rtsp://localhost:8554/ds-test`

```bash
python3 deepstream_yolov7-triton-server_rtsp_out.py -i <input_files> -m <model> -c <codec> -b <bitrate> [--rtsp-ts]

#example
python3 deepstream_yolov7-triton-server_rtsp_out.py  \
-i file:///videos/input.mp4 rtsp://myserver:554  \
-m  yolov7_qat \
-c H264   
```


### Arguments 
*   `-i`, `--input`: Path to input `file://` or `rtsp://` elementary stream. Multiple input files can be provided.
*   `-m`, `--model`: Choose between 'yolov7' or 'yolov7\_qat'. (Default: 'yolov7\_qat')
*   `-c`, `--codec`: RTSP Streaming Codec. Choose between H264 and H265. (Default: H264)
*   `-b`, `--bitrate`: Set the encoding bitrate. (Default: 4000000)
*   `--rtsp-ts`: Attach NTP timestamp from RTSP source. (Default: False)

<br><br><br> 


