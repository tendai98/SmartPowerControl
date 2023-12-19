# Power Control System 🛠️💡

This project utilizes an ESP8266 microcontroller, a single-channel relay, and an ACS712 current sensor to control power consumption.

## Project Overview 📝

### Project Structure
- **Code Files:**
  - `power.h`: Manages the power control functions.
  - `server.h`: Handles communication and server setup.
  - `SmartPowerControl.ino`: Contains the main logic and setup for the project.
  - `wifi.h`: Manages Wi-Fi connectivity and setup.

### Code Functionality

#### Power Control
- **`initACS()`:** Initializes the ACS712 current sensor and sets up the relay control pin.
- **`currentReading()`:** Reads the current value based on the selected mode (AC or DC).
- **`controlRelayState(boolean state)`:** Controls the relay state based on the received command.
- **`systemControl(unsigned int opcode)`:** Handles various system control operations, such as turning the relay on/off, changing current mode, and system reset.

#### Server and Communication
- **`getCurrentData()`:** Sends the current reading to the connected client.
- **`startServer()`:** Starts the web server to handle incoming requests.
- **`scanServerData()`:** Scans for incoming data from the server/client and triggers appropriate system control based on received commands.

#### Wi-Fi Initialization
- **`initWiFi()`:** Initializes the ESP8266 module and sets it in Access Point mode, allowing client devices to connect.

## Usage 🚀

1. **Hardware Setup:**
   - Connect the ACS712 current sensor and the relay module to the ESP8266 as per the defined pin configurations.
2. **Code Upload:**
   - Upload the provided code (`SmartPowerControl.ino`) to the ESP8266 using the Arduino IDE or compatible software.
3. **Interaction:**
   - Connect to the Wi-Fi network named "Controller-0" using the password "root12345".
   - Send specific commands (e.g., to switch the relay on/off, change current modes) to the ESP8266 module via a client program or HTTP requests.

## Additional Notes ℹ️

- Customize pin configurations and sensor settings in the code according to your hardware connections.
- Ensure proper power supply and connectivity for stable operation.
- Exercise caution and proper safety measures while working with electrical components.
