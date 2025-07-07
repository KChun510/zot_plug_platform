# ZotPlug Firmware

Full-stack Infrastructure & Firmware for our ZotPlug smart plug system. 

## Dependencies

- Arduino CLI for building and flashing
- ESP32 Board Package via Arduino CLI
- PubSubClient and EmonLib Arduino libraries
- MQTT broker (e.g., Aedes) running on your local network
- Serial monitor tool (arduino-cli monitor, minicom, etc.)
- mqtt-pattern node.js package

## Flashing & Monitoring

```bash
arduino-cli compile --fqbn esp32:esp32:esp32 .
arduino-cli upload -p /dev/ttyUSB0 --fqbn esp32:esp32:esp32 .
arduino-cli monitor -p /dev/ttyUSB0 -c baudrate=115200
```
## 🛠️ Hardware Development Workflow

### **Pre-requisites**  
1. Install **Node.js** and **npm**  
   [https://docs.npmjs.com/downloading-and-installing-node-js-and-npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

2. Navigate to the broker directory  
   ```bash
   cd ./zot_plug/infra/broker_mqtt
   ```

3. Install project dependencies  
   ```bash
   npm install
   ```
### **Dev-Steps**  
1. **Update Network Config**  
   Open `./infra/broker_mqtt/server.ts` and update your network credentials.

2. **Run the MQTT Broker**  
   From the project root, run:

   ```bash
   npx tsx ./infra/broker_mqtt/server.ts
   ```
3. **Develop Firmware**
   Navigate to:
   ```bash
   ./esp_client/src
   ```
4. **Flash & Test**  
   Reflash the ESP32 and test against your local broker.

## 📡 Network Notes

- Ensure your computer and the ESP32 are on the same WiFi network.
- Default MQTT port: 1883

## 📝 Setup Documentation

For complete setup instructions, see the [Setup Guide on Google Docs](https://docs.google.com/document/d/1jFlQuHnFwy8aJPPMJ6DQvYgvtMj_6Ua5th_mMhYTuXo/edit?usp=sharing).




