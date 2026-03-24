# Power Management and Distribution
<p align="center">
  <img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/7a3563c2-9570-4edb-b36d-11212189c005" />
</p>
The power management PCB regulates the battery voltage and interfaces with the other PCBs by distributing +5 V to an ESP32 and three motor drivers on the motor control PCB and to another ESP32 and a gimbal servo on the camera stabilization PCB. This is performed using output connectors on the power management PCB, which connect to input connectors on the other PCBs through 20 AWG wires. Protection circuits and fuses are also implemented at the battery connector and at the voltage input of each buck converter. 	

# Motor Control
<p align="center">
  <img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/13d84bf3-59a6-424f-a424-96e139d74a8e" />
</p>
For motor control, the XBox controller sends joystick inputs through Bluetooth to the ESP32, which then controls the motor drivers to move six wheel motors. The motor drivers and ESP32 receive power from the power management PCB.

# Camera Stabilization
<p align="center">
  <img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/5ffe2648-65d2-47c5-99eb-d9ea1200eb0c" />
</p>
For camera stabilization, the IMU communicates with the ESP32 via an I2C interface, where the IMU connects to the SCL and SDA pins on the ESP32. The ESP32 receives data from the IMU to control the gimbal servo. The gimbal servo and ESP32 also receive power from the power management PCB, and the IMU receives +3.3 V from the ESP32. 
