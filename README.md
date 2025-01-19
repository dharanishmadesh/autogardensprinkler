# Automatic Plant Watering System Using Arduino🌱💧

This project demonstrates an **automatic plant watering system** using an Arduino board. The system continuously monitors soil moisture levels using a sensor and activates a pump when the soil is too dry. This setup ensures your plants always get the water they need without manual intervention. 🪴✨

---

## Features 🚀
- **Soil Moisture Monitoring**: Reads real-time moisture levels from the soil.
- **Automatic Watering**: Activates a pump when moisture levels fall below a threshold.
- **Energy Efficient**: Operates only when necessary, saving power and water.
- **Simple Setup**: Easy to build and program for hobbyists and beginners.

---

## Components Required 🛠️

1. **Arduino Board** (e.g., Uno, Nano)  
2. **Soil Moisture Sensor**  
3. **Water Pump**  
4. **Resistors and Connecting Wires**  
5. **Power Source**  
6. **Breadboard** (optional)

---

## Circuit Diagram ⚡

- Connect the **soil moisture sensor** to analog pin `A0`.
- Connect the **pump** to pin `6` via a transistor or relay (depending on your pump's power requirements).
- Ensure all components share a common ground.

---

## Code 📜
```cpp
#define sensor A0
#define pumb 6

void setup() {
  Serial.begin(9600);
  pinMode(sensor, INPUT);
  pinMode(pumb, OUTPUT);
}

void loop() {
  int moisture = analogRead(sensor);
  Serial.println(moisture);

  if(moisture > 750) {
    analogWrite(pumb, 125);
  } else {
    analogWrite(pumb, 0);
  }
}
```

---

## How It Works 🌟
1. **Moisture Detection**: The soil moisture sensor measures the water content in the soil and sends an analog signal to the Arduino.
2. **Data Processing**: The Arduino reads the sensor value and determines if the soil is dry (sensor value > 750).
3. **Pump Activation**: When the soil is dry, the Arduino activates the water pump by sending a PWM signal to pin `6`. If the soil is moist, the pump remains off.
4. **Serial Monitoring**: Moisture values are displayed in the Serial Monitor for real-time tracking.

---

## Threshold Adjustment 🎛️
- The threshold value (`750`) can be adjusted in the code based on your soil type and plant requirements.

---

## Usage Instructions 📖
1. Assemble the circuit as per the diagram.
2. Upload the provided code to your Arduino board.
3. Open the Serial Monitor (set to 9600 baud) to observe moisture readings.
4. Place the sensor in the soil and connect the water pump to a water source.
5. Power the Arduino, and the system will start monitoring and watering automatically.

---

## Safety Tips ⚠️
- Ensure proper insulation to avoid water damage to electronic components.
- Use a relay module or transistor to safely drive the pump.
- Avoid overwatering by fine-tuning the moisture threshold.

---

## Future Enhancements 🌈
- Add a **Blynk app integration** for remote monitoring and control.
- Include a **water level sensor** to monitor the pump's water source.
- Integrate a **temperature sensor** for smarter irrigation based on weather conditions.
- Upgrade to solar-powered operation for energy efficiency.

---

## License 📄
This project is open-source under the **MIT License**. Feel free to modify and share it!

---

Happy Coding! 💻✨

