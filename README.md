# Bluetooth Remote Control Car
Bluetooth Remote Control Car is an ESP32-based project that can avoid obstacles.
 

## Components

<img src="https://github.com/mahfuzhasanreza/Bluetooth-RC-Car/assets/115473925/972e9ed8-9540-4640-b1a2-f3ce218c6164" alt="Components" height="450">

## Components Details  

- **ESP32**: For development puposes, we use this board.  

- **L298N Motor Driver**: It controlled the motors.  

- **4 DC Motors and Wheels**: It is used for moving the car (driving).  

- **2 18650 Battery (Rechargeable)**: It is used for providing voltageto the circuit.

- **Car Chassis (Optional)**: The main body to attach othercomponents (can use any PVC or cardboard as a base).

- **Jumper Wires**: Male-to-male and male-to-female connectors forthe circuit (any normal wires can be used, though male-to-femaleconnectors are necessary for connecting with esp).

- **Breadboard (Optional)**: For connection the wires with otherscomponents we used this board.

## Following Steps

1. First we attached the motors to a base.   

   

2. Then connected both left motor's positive terminals to "outl" and negative terminals to "out2" of the L298N driver.

3. And repeated the process for the right motors and connected them to "out3" and "out4" of the motor driver.
    
   <img src="https://github.com/megersam/esp32-bluetooth/assets/77697719/3224f104-ab98-45b1-bde7-97019fd08fbf" alt="step-3" height="450"> 
 


4. After that connected the battery with the motor driver. Positive terminal to 12V marked port. We marged the ground of the battery with the ESP32 ground connector to and connected it with the GND marked port. Lastly we connected the 5v from our ESP32 with the 5V maked port beside the GND of the driver so that the ESP32 board can take power from the motor driver.

5. We connected the ENA, IN1, IN2, IN3, IN4, ENB ports with the ESP32's D32, D26, D27, D13, D12 & D33 no pin respectively.
 


6. We removed both of the ENA and ENB jumpers so that we can control the speed of the motors using PWM. If anyone doesn't want to control the speed of the motors then they should leave the jumper on the board.

7. Then we downloaded the "[Bluetooth RC Controller](https://bluetooth-rc-car.en.softonic.com/android)" app from the play store or website and started writing our code according to the input values the app passes via bluetooth.

## Circuit Diagram


<img src="https://github.com/megersam/esp32-bluetooth/assets/77697719/2c7a33ff-0d09-4182-aebb-0b97ad621d45" alt="circuit-diagram" height="450">


## Internal Control

- The bluetooth car app sends different characters for different functions and the ESP receives them and controlsthe motors using the L298N motor driver module.  
Forward → ‘F’  
Back → ‘B’  
Left → ‘L’  
Right → ‘R’

- To move forward the In1 and In3 gets HIGH and In2 and In4 gets LOW. and we send the PWM value to both ENA and ENB pins. So, all motors run forward according to the value from PWM.
  
- To move Backward the In1 and In3 gets LOW and In2 and In4 gets HIGH. We send the PWM value to both ENA and ENB pins. So, all motors run Backward according to the value from PWM.
  
- To move Left the In1 and In4 gets LOW and In2 and In3 gets HIGH. As a result the left runs backwards and the right motors run forward and the car turns left.

- To move Right the In1 and In4 gets HIGH and In2 and In3 gets LOW. As a result the right motors run backwards and the left motors run forward and the car turns right.

- From the speed setter function of the app we can send values from 1 to 9 and ‘q’. So we set different speed values for these inputs in the ESP32. So the car can run at different speeds.

 
 


## Pictures and Videos

   
<!-- <img src="https://github.com/mahfuzhasanreza/Bluetooth-RC-Car/assets/115473925/c71b7d87-ad7a-4ff5-aec2-d232ff369ffa" alt="img-3" height="350">
<img src="https://github.com/mahfuzhasanreza/Bluetooth-RC-Car/assets/115473925/a78ed5b9-98d9-4214-9f14-465a4c1eef42" alt="img-4" height="350"> -->

 
