# RC Car Camera Robot ESPHome
## Version 1.0

 - Control a Camera wherever you want in your House with this RC Car Camera. 
 - Control car speed.
 - Control away from home like everything in HA.
 - Works when it's charging so it's possible to move the camera where you want.
 - Battery docker station.

<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/esphome_logo_logo.png" width="200" />

<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/ha_logo.png" width="100" height="100" />

[![](https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/Screenshot_20220409-140909.png)](https://youtu.be/ULK-bejEP4k)


<p align="center">
  https://youtu.be/ULK-bejEP4k

I am not an electronics, programming or espHome expert. I have been searching, getting inspiration from videos and looking for information until I put the pieces together. What I am is a big fan of Home Assistant with a multitude of home automation devices, even addicted :).


<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/rc_car_v_0_1_picture_1.jpg" width="350" />


I've tried with only an esp32cam but I can't get it to work, so I put it aside in the same battery.

 EVERYTHING IS QUITE PROVISIONAL, and has not been assembled yet, when I have all the pieces I will soldering and update this page 

<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/rc_car_v_0_1_picture_2.jpg" width="350" />

INSPIRATION:

https://www.amazon.es/dp/B06XKC6Q86/ref=cm_sw_r_apan_i_AA99JTHV7PV2H54CWFJE?_encoding=UTF8&psc=1
https://youtu.be/tyY7AN132Xs
https://youtu.be/aJeD7R48ZyI
https://github.com/ishakmuhamad/rc-car-homeassistant

MATERIALS:

 - Esp8266 nodemcu board
 - Esp32 cam board
 - 12V Battery 6800mah Li-ion Rechargeable Battery with Protection Board and Charger
https://a.aliexpress.com/_vECinm
 - Arduino Car Kit with 4 TT motors and wheels
https://a.aliexpress.com/_ugpMKk
 - Servo Pan Tilt it depends on the weight of the camera:
 - Servo PT Pan/Tilt for 2 servo motors sg90 or mg90s 360º, in my case the sg90 sometimes it doesn't have enough strength to move up a Xiaofang Camera.
https://a.aliexpress.com/_vaiPQg 

Or
 -  MG996 Pan/Tilt for 2 servo motors MG996 
https://a.aliexpress.com/_v7d13E
 - 2 servo motors  SG90 or Mg90 360º

Or
 - 2 servo motors MG996 360º
https://a.aliexpress.com/_vYO1g4
 - Dupont Cables
 https://a.aliexpress.com/_vOOCXW
 - USB Voltage Regulator DC-DC Charger or a Portable Battery for the usb camera
https://a.aliexpress.com/_vLq7TC
 - rtsp USB Camera (Xiaomi Xiaofang in my case) because I want a better image quality and night vision
 - 12.6 Battery indicator
https://a.aliexpress.com/_vnwGzs

 
OPTIONAL: 

  - Soldering PCB boards
https://a.aliexpress.com/_vnVAiM
  - Led lights.
https://a.aliexpress.com/_vkivtW
  - Transistors
  - Ohms
  - 3d printed case for battery docker station

DIAGRAM CONNECTION:

<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/Diagram RC Camera Car.png" width="350" />


FILE CONFIGURATION:

 - Plug your esp8266 in your computer or Raspberry Pi. Select new device in EspHome and choose nodemcuv2. Give a name like RC-Car
 - Copy and paste the content of RC-Car.yaml file in your file, change your ssid and WiFi password validate it and install it. 
 - Then several entities should appears at Home Assistant:
     - switch.input1
     - switch.input2
     - switch.input3
     - switch.input4
     - light.car_speed
     - light.led_cam
     - service: esphome.rc_car_control_servo_x
     - service: esphome.rc_car_control_servo_y 
 - You have to create two input numbers in helpers from min -100 and max 100 with slider, like this names:
     - input_number.servo_x
     - input_number.servo_y
 - Once created this input_numbers them copy and paste the content of automations.yaml in your automation.yaml or take it as an example and create it in the UI settings
 - Also copy and paste the content of scripts.yaml into your scripts.yaml file or take it as an example and create it in the UI settings
 - In your Home Assistant Lovelace or Dashboard:
     - Create a Camera Live Card 
     - Create a Grid card with all buttons (example if you want to paste in code)
     - Create a Speed Controller using light.speed_control entity with slider 
     - Create a entities card with input_number.servo_x and input_number.servo_y
     - Create a Camera auto Card
 - Plug your esp32cam in your computer or Raspberry Pi. Select new device in EspHome and choose esp32dev. Give a name like RC-Car-32cam.
 - Copy and paste the content of RC-Car-32cam.yaml file in your file, change your ssid and WiFi password validate it and install it.
 - Then other several entities should appears at Home Assistant:
     - camera.rc_car_32_cam 
     - light. led_rc_car_camera
     - sensor.camara1_ esphome _version
     - switch.rc_car32cam_restart
     - binary_sensor. rc_car32 cam_status
     - sensor.camara1_wifi_signal_sensor
     - sensor.uptime_sensor
 - Thats It! Have a good time!

<p align="center">
  <img src="https://github.com/janfajessen/EspHome-RC-FPV-Car-Robot-ve0.1-Esp8266-pantilt-Servo-motors-Camera-USB-led-L298N---Home-Assistant/blob/main/Screenshot_20220411-093548.png" width="250" />

QUESTIONS:

 - How to know the battery status?
 - How to connect 2 or more led lights to same pin with transistors and ohms?

You can answer here:
https://community.home-assistant.io/t/esphome-rc-fpv-car-robot-esp8266-pantilt-servo-motors-camera-usb-led-l298n/410117?u=janinho


TO DO OR WISHLIST:

- It con use only a esp32camera without the esp8266 board.
- Add 1 or 3 more front lights, maybe also 4 backlights using ohms and transistors
- Fix the way the sensor battery, know the correct pins or correct code
- 3d printed battery docker station "like a robot vacuum"





#esphome #rccar #rccars #rc #homeassistant #L298N #ttmotors #esp8266 #esp32cam #fpv #fpvcar #fpvwifi #wificar #rcwifi #car #cars #wirelessrccar #radiocontrol #esphomerobot #robotcar #robotcar #esphomecar #esphomeproject #esphomeservo #esphomepantilt

