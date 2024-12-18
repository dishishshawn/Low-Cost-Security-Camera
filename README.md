# Low-Cost Security Camera

This project utilizes the ESP32-CAM AI-Thinker module to create an affordable home security camera system.

## Features

- **Live Video Streaming:** Access real-time video feed over Wi-Fi.
- **Motion Detection:** Receive alerts when movement is detected.
- **Image Capture:** Automatically capture and store images upon motion detection.
- **Remote Access:** Monitor your camera feed from anywhere via the internet.

## Hardware Requirements

- [ESP32-CAM AI-Thinker module](https://github.com/raphaelbs/esp32-cam-ai-thinker)
- FTDI USB to TTL Serial Adapter for programming
- External 5V power supply
- MicroSD card (optional, for image storage)

## Software Requirements
- Arduino IDE with ESP32 board support
- ESP32 Camera Library
- Additional Arduino libraries:
  - WiFi
  - ESPAsyncWebServer
  - ArduinoJson

## Setup Instructions

1. **Hardware Setup:**
   - Connect the ESP32-CAM to the FTDI adapter:
     - ESP32-CAM GND to FTDI GND
     - ESP32-CAM 5V to FTDI VCC (5V)
     - ESP32-CAM U0R to FTDI TX
     - ESP32-CAM U0T to FTDI RX
     - GPIO0 to GND (for flashing mode)
   - Ensure a stable 5V power supply to the ESP32-CAM to prevent brownout issues.

2. **Software Setup:**
   - Install the [Arduino IDE](https://www.arduino.cc/en/software).
   - Add ESP32 board support to the Arduino IDE.
   - Install the necessary libraries:
     - ESP32 Camera Library
     - ESPAsyncWebServer
     - ArduinoJson
   - Configure the Arduino IDE:
     - Select "AI Thinker ESP32-CAM" as the board.
     - Choose the appropriate COM port.
   - Open the provided sketch and update Wi-Fi credentials:
     ```cpp
     const char* ssid = "your_SSID";
     const char* password = "your_PASSWORD";
     ```
   - Upload the sketch to the ESP32-CAM:
     - Hold the ESP32-CAM in flashing mode by connecting GPIO0 to GND.
     - Click the upload button in the Arduino IDE.
     - After uploading, disconnect GPIO0 from GND and reset the board.

3. **Accessing the Camera Feed:**
   - Open the Serial Monitor in the Arduino IDE to find the IP address assigned to the ESP32-CAM.
   - Enter the IP address in a web browser to access the live video stream.

## Troubleshooting

- **Brownout Detector Errors:** Ensure the ESP32-CAM receives a stable 5V supply.
- **Camera Initialization Failed:** Verify the camera module is properly connected and not damaged.
- **No IP Address Assigned:** Check Wi-Fi credentials and ensure the network is operational.

## References

- [ESP32-CAM AI-Thinker Module Specifications](https://github.com/raphaelbs/esp32-cam-ai-thinker)
- [ESP32-CAM Video Streaming and Face Recognition with Arduino IDE](https://randomnerdtutorials.com/esp32-cam-video-streaming-face-recognition-arduino/)

## License

This project is licensed under the MIT License.

---

*Note: This project is inspired by various open-source contributions and aims to provide a cost-effective solution for home security using the ESP32-CAM module.* 
