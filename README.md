# Power Control System 🛠️💡

This project utilizes an ESP8266 microcontroller, a single-channel relay, and an ACS712 current sensor to control power consumption.

## Project Overview 📝

### Project Structure
- **Code Files:**
  - `power.h`: Manages the power control functions.
  - `server.h`: Handles communication and server setup.
  - `SmartPowerControl.ino`: Contains the main logic and setup for the project.
  - `wifi.h`: Manages Wi-Fi connectivity and setup.

### Key Functions and OpCodes

#### Power Control
- **`systemControl(unsigned int opcode)`:** Handles various system control operations based on opcodes received.
  - **OpCodes:**
    - `#define RELAY_ON_OPCODE 0x11AA`: Turns the relay on.
    - `#define RELAY_OFF_OPCODE 0x22BB`: Turns the relay off.
    - `#define RESET_OPCODE 0x33CC`: Resets the system.
    - `#define DC_CURRENT_MODE 0x44DD`: Sets the device mode to DC current.
    - `#define AC_CURRENT_MODE 0x55EE`: Sets the device mode to AC current.

#### Server and Communication
- **`scanServerData()`:** Scans for incoming data from the server/client and triggers appropriate system control based on received commands.
- **`startServer()`:** Starts the web server to handle incoming requests.
- **`getCurrentData()`:** Sends the current reading to the connected client.

### Wi-Fi Initialization
- **`initWiFi()`:** Initializes the ESP8266 module and sets it in Access Point mode, allowing client devices to connect.
