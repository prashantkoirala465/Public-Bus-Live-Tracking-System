# Public Bus Live Tracking System

## TECH 100 Project Overview
This project was developed as part of the TECH 100 course, demonstrating the practical application of IoT technologies in public transportation. The system enables real-time tracking of public buses using ESP8266 microcontroller and GPS module integration.

## Features
- Real-time GPS tracking of bus locations
- Web-based interface for location visualization
- Google Maps integration for accurate mapping
- Responsive design for mobile and desktop viewing
- 5-second location update interval
- Modern UI with custom styling

## Hardware Requirements
### Components
1. NodeMCU ESP8266 Development Board
2. NEO-7M GPS Module
3. Connecting wires
4. USB cable for programming
5. Power source (USB power bank recommended for mobility)

### Technical Specifications
- **ESP8266 Operating Voltage:** 3.3V
- **GPS Module Operating Voltage:** 3.3V-5V
- **Serial Communication:** 9600 baud rate for GPS module
- **WiFi:** 2.4GHz IEEE 802.11 b/g/n

## Software Requirements
### Required Libraries
1. `SoftwareSerial.h` - For serial communication with GPS module
2. `TinyGPS++.h` - For parsing GPS data
3. `ESP8266WiFi.h` - For WiFi connectivity

### Development Environment
- Arduino IDE
- Required Board Manager: ESP8266 Community Board Package

## Wiring Instructions
### GPS Module to NodeMCU Connections
- GPS VCC → NodeMCU 3.3V
- GPS GND → NodeMCU GND
- GPS TX → NodeMCU D1 (GPIO 4)
- GPS RX → NodeMCU D2 (GPIO 5)

Refer to the wiring diagram in `nodemcu-gps-wiring.png` for visual guidance.

## Setup Instructions

### 1. Hardware Setup
1. Connect the GPS module to NodeMCU following the wiring instructions above
2. Power up the NodeMCU using a USB cable or power bank

### 2. Software Setup
1. Install Arduino IDE
2. Add ESP8266 board support:
   - Go to File → Preferences
   - Add `http://arduino.esp8266.com/stable/package_esp8266com_index.json` to Additional Board URLs
   - Go to Tools → Board → Boards Manager
   - Search for and install "esp8266"

3. Install Required Libraries:
   - Go to Sketch → Include Library → Manage Libraries
   - Install "TinyGPS++" library
   - ESP8266WiFi comes with the ESP8266 board package

### 3. Configuration
1. Open `public_bus_live_tracking_system.ino`
2. Update WiFi credentials:
   ```cpp
   const char *ssid = "your_wifi_ssid";
   const char *password = "your_wifi_password";
   ```
3. Add your Google Maps API key:
   ```cpp
   String GMAP_API_KEY = "your_google_maps_api_key";
   ```

### 4. Upload Code
1. Select appropriate board: Tools → Board → NodeMCU 1.0
2. Select correct COM port
3. Upload the code

## Usage Guide
1. Power up the device
2. Wait for WiFi connection (Serial monitor will display IP address)
3. Open the displayed IP address in a web browser
4. The map will show the current location with updates every 5 seconds

## System Architecture
### Hardware Layer
- ESP8266 handles WiFi connectivity and serves the web interface
- NEO-7M GPS module provides location data
- Serial communication between GPS and ESP8266

### Software Layer
- Arduino framework for device programming
- TinyGPS++ for GPS data parsing
- ESP8266WebServer for serving web interface
- Google Maps API for location visualization

### Web Interface
- Responsive HTML/CSS design
- JavaScript for map handling and updates
- Google Maps integration for location display

## Troubleshooting
### Common Issues
1. **No GPS Fix**
   - Ensure clear view of sky
   - Wait for GPS module to acquire satellites (can take 1-5 minutes)
   - Check GPS module connections

2. **WiFi Connection Issues**
   - Verify WiFi credentials
   - Ensure WiFi network is in range
   - Check Serial monitor for connection status

3. **Map Not Loading**
   - Verify Google Maps API key
   - Check browser console for errors
   - Ensure device is connected to internet

## Future Enhancements
- Multiple bus tracking support
- Route prediction
- Estimated arrival times
- Historical route data logging
- Mobile app development

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

### Guidelines
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- TECH 100 course instructors and teaching assistants
- ESP8266 Community
- TinyGPS++ library developers
- Google Maps Platform

## Contact
For any queries regarding this project, please open an issue in the repository.

---
*This project was developed as part of the TECH 100 course curriculum.*