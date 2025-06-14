# SRS WebRTC Streaming Server

This is a streaming server project using SRS (Simple RTMP Server) with WebRTC support. The project includes tools for monitoring bandwidth usage in WebRTC streams.
<img width="1135" alt="Screenshot 2025-05-29 at 16 57 37" src="https://github.com/user-attachments/assets/854362d5-4414-422c-b31a-f8670371f6a7" />

## Key Features

- SRS Server with WebRTC support
- WebRTC Publisher with bandwidth monitoring
- WebRTC Player with bandwidth monitoring
- Docker Compose setup for easy deployment
- FFmpeg test pattern generator for bandwidth testing

## Getting Started

### System Requirements

- Docker and Docker Compose
- Web browser with WebRTC support (Chrome, Firefox, Edge, etc.)
- Python 3 (for test pattern generator)
- FFmpeg (for test pattern generator)

## Configuration

- SRS server configuration is in `srs.conf`
- WebRTC is configured to use port 8000/udp
- RTMP is available on port 1935
- HTTP API is available on port 1985
- HTTP server for web pages runs on port 8090

## Technical Details

### Bandwidth Monitoring

- Uses WebRTC Stats API for bandwidth monitoring
- Publisher page calculates outgoing bandwidth in kbps
- Player page calculates incoming bandwidth in kbps
- Both pages display video resolution, frame rate, and codecs in use

### Testing Tools

- Uses FFmpeg to create high-quality video streams
- Supports multiple formats and configurations
- Customizable parameters like bitrate and resolution

## Troubleshooting

### Access Issues

- Check camera/microphone permissions in browser
- Ensure required ports are open

### Network Issues

- Verify WebRTC UDP port 8000 accessibility
- View Docker logs using `docker logs srs-webrtc`

### FFmpeg Issues

- Verify FFmpeg installation
- Confirm input parameters are correct

## System Architecture

```
[WebRTC Browser Publisher] ---> [SRS Server] ---> [WebRTC Browser Player]
      (index.html)                (Docker)           (player.html)
```

## Usage Guide

1. Start the system:

   ```bash
   docker-compose up -d
   ```

2. Access web pages:

   - Publisher: http://localhost
   - Player: http://localhost/player.html

3. Monitor bandwidth:
   - Use test pattern tool
   - Monitor metrics on web interface

## License

This project is open source and distributed under the MIT License.
