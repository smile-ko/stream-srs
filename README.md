# SRS WebRTC Streaming Server

This repository contains a setup for streaming with SRS (Simple RTMP Server) using WebRTC. It includes tools to test bandwidth usage for WebRTC streams.
<img width="1242" alt="Screenshot 2025-05-29 at 16 56 48" src="https://github.com/user-attachments/assets/5956dbde-2fe8-446b-af83-87c19cf66a32" />


## Features

- SRS Server with WebRTC support
- WebRTC Publisher with bandwidth monitoring
- WebRTC Player with bandwidth monitoring
- Docker Compose setup for easy deployment
- FFmpeg test pattern generator for bandwidth testing

## Getting Started

### Prerequisites

- Docker and Docker Compose
- Web browser with WebRTC support (Chrome, Firefox, Edge, etc.)
- Python 3 (for the test pattern generator)
- FFmpeg (for the test pattern generator)

## Configuration

- The SRS server configuration is in `srs.conf`
- WebRTC is configured to use port 8000/udp
- RTMP is available on port 1935
- HTTP API is available on port 1985
- HTTP server for web pages is on port 8090

## Technical Details

- The bandwidth monitoring is implemented using the WebRTC Stats API
- The publisher page calculates outgoing bandwidth in kbps
- The player page calculates incoming bandwidth in kbps
- Both pages display video resolution, frame rate, and codecs in use
- The test pattern generator uses FFmpeg to create a high-quality stream

## Troubleshooting

- If you cannot access the camera, make sure your browser has camera/microphone permissions
- For network issues, check if WebRTC UDP port 8000 is accessible
- Docker logs can be viewed with `docker logs srs-webrtc`
- For FFmpeg test pattern issues, ensure FFmpeg is installed correctly

## Architecture

```
[Browser WebRTC Publisher] ---> [SRS Server] ---> [Browser WebRTC Player]
      (index.html)                (Docker)           (player.html)
```

## License

This project is open source and available under the MIT License.
