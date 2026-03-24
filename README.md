**Project Demo Video:** https://www.youtube.com/watch?v=6TupsFSBIgM

**Reconnaissance Vehicle Final Design**
<p align="center">
  <img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/689fcb73-f903-4e4b-9c4e-92715f6aaf98" />
</p>

**Reconnaissance Vehicle System Block Diagram**
<p align="center">
  <img width="2716" height="1262" alt="image" src="https://github.com/user-attachments/assets/6e77e5ff-7609-4cb5-8dac-f92ec6807177" />
</p>

The image above shows the high-level system block diagram of the reconnaissance vehicle. The block diagram features four major subsystems: power management, motor control, camera stabilization, and computer vision. Power management, motor control, and camera stabilization are implemented as PCBs on the vehicle. For power management, the power source is a LiPo battery, where this subsystem steps down the battery’s voltage using buck converters to a stable +5 V. The output is then distributed to supply electronics such as two ESP32 microcontrollers, three motor drivers, and a gimbal servo in the motor control and camera stabilization subsystems, while ensuring protection between the buck converters and the battery. 

Next for motor control, the ESP32 receives commands from an Xbox Controller via Bluetooth to control the speed and direction of six motors driven by three motor drivers using PWM signals. Additionally, in the camera stabilization subsystem, an IMU communicates with another ESP32 to send data on the vehicle's orientation during traversal. This ESP32 then controls the gimbal servo to stabilize the camera based on the vehicle’s orientation. 

Finally, the computer vision subsystem features a Raspberry Pi 5 powered by a remote power supply called the UPS Hat. The Pi receives camera feed inputs from a webcam to run the human and hazard detection models using OpenCV through WiFi, where the machine learning models are displayed on a live server using Flask.
