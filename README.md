## 🚀 IR Sensor & LED Control System

This project connects an ESP32 to Wi-Fi, uses an IR sensor to detect the presence of an object, and communicates the detection status through an MQTT broker.
Alao allows controlling an LED remotely via MQTT application.

### 📲 Features

  .	Detects if an object is present or not using IR sensor.  
  •	Publishes the detection status to the MQTT topic.  
	•	Listens to MQTT messages to turn an LED on or off remotely.  
	•	Keeps the MQTT connection alive and reconnects if needed. 
 

 ### 🧩 Used Technologies

  •	ESP32 Wi-Fi Microcontroller    
	•	MQTT Protocol (with EMQX broker)   
	•	Arduino IDE for programming   
	•	WiFi.h and PubSubClient.h libraries 

 ### ⚙️ Hardware Tools

  •	ESP32 board
	•	IR sensor module  
	•	LED  
	•	Resistor  
	•	Breadboard and jumper wires  


 ### 🛠 Circuit

  •	IR sensor connected to GPIO 4 (input).   
	•	LED connected to GPIO 18 (output) with a resistor.    

 ### 📡 MQTT topics

 | Topic | Purpose | Payload |
|----------|----------|----------|
| 	/sector/farida/ir    | Publish the IR sensor status    | OBJECT_DETECTED / NO_OBJECT_DETECTED |
| /sector/farida/led    | Subscribe to LED control    | LED_ON / LED_OFF |

### 🤖 Working Mechanism


  1.	ESP32 connects to the Wi-Fi network.
	2.	Connects to the MQTT broker.
	3.	Continuously monitors the IR sensor:	Publishes “OBJECT_DETECTED” or “NO_OBJECT_DETECTED” based on object presence.
	5.	Listens for incoming MQTT messages to turn the LED ON or OFF.
	6.	Updates LED status based on received commands.

### 📝 Notes

 
 •      The device will publish a status update every 3 seconds.  
	•	If disconnected from Wi-Fi or MQTT, the ESP32 will attempt to reconnect automatically.   
	•	QoS level 0 (at most once) is used for will message settings on the broker.   

### 📞 Contact

For any questions, feel free to reach out:
Email: [asmaasalaheldin586@gmai.com]


 
