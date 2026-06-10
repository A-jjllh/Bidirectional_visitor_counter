📊 Bidirectional Visitor Counter using IR Sensors
5
🚀 Overview

This project implements a Bidirectional Visitor Counter using two IR sensors and an Arduino. It detects the direction of movement (entry/exit) and maintains:

👥 Current number of people inside
📈 Total number of people entered

The system is designed for applications such as:

Smart classrooms 🏫
Office occupancy monitoring 🏢
Retail analytics 🛒
IoT-based automation systems
⚙️ How It Works

Two IR sensors are placed at a doorway:

Sensor 1 → Sensor 2 → Person enters
Sensor 2 → Sensor 1 → Person exits

The system uses:

Sequence detection logic
Debouncing to avoid false triggers
Time window validation to confirm valid movement
🧠 Core Logic

The logic is based on detecting the order of sensor activation within a specific time window.

Entry Detection:

IR1 → IR2  ⇒  Entry

Exit Detection:

IR2 → IR1  ⇒  Exit

Current Count:

Current = Total Entered - Total Exited
🔌 Hardware Requirements
Arduino (Uno / Nano / Mega)
2 × IR Sensors (Active LOW)
Jumper wires
Breadboard (optional)
USB cable for programming
🖥️ Circuit Diagram
4
Connections:
Component	Arduino Pin
IR Sensor 1	D2
IR Sensor 2	D3
VCC	5V
GND	GND
💻 Software Requirements
Arduino IDE
📂 Code Explanation
🔹 Pin Configuration
const int irPin1 = 2;
const int irPin2 = 3;
🔹 Counters
int in_count = 0;
int out_count = 0;
int current_count = 0;
🔹 Timing Controls
const unsigned long sequenceWindow = 400;
const unsigned long debounceMs = 30;
const unsigned long reportInterval = 500;
🔹 Key Features
Debouncing logic prevents false triggers
Sequence window (400ms) ensures valid movement detection
Real-time serial output
Safety check to prevent negative counts
📟 Output (Serial Monitor)
Current Count: 3    Total Entered: 10
🧪 Testing Instructions
Upload the code to Arduino
Open Serial Monitor (Baud Rate: 115200)
Simulate movement:
Pass object/person from Sensor 1 → Sensor 2 → Entry
Pass from Sensor 2 → Sensor 1 → Exit
Observe updated counts in real-time
🔍 Features
✅ Direction detection (Entry/Exit)
✅ Real-time monitoring
✅ Debounce protection
✅ Lightweight and efficient code
✅ Easy to extend (LCD, IoT dashboards, etc.)
⚡ Future Improvements
📺 Add LCD/OLED display
🌐 Integrate with IoT platforms (Blynk / Firebase)
📊 Store data in cloud/database
🔔 Add alerts when occupancy exceeds limit
📁 File Structure
Bidirectional_counter.ino
README.md
📌 Notes
Sensors are configured as INPUT_PULLUP
IR sensors are active LOW
Proper alignment is critical for accurate detection
🧑‍💻 Author

Your Name
IoT Internship Project

📜 License

This project is open-source and available under the MIT License.
