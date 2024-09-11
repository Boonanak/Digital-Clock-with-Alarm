<h1>Digital Clock with Alarm</h1>

 ### [YouTube Demonstration (In Work)](INSERTLINK)

<h2>Description</h2>
In this Digital Clock project, an Arduino Uno is programmed to control a functional clock system. Users can set both the current time (hours and minutes) and the alarm time through a user interface consisting of buttons. The current time is continuously displayed on a Liquid Crystal Display (LCD) with optional backlighting for better visibility. The clock is powered through a USB connection with the Arduino. When the set alarm time is reached, a piezo buzzer sounds and the clock stops. The system is programmed using the Arduino IDE and includes error handling to manage incorrect time or alarm settings.
<br />


<h2>Environments Used </h2>

- <b>EasyEDA</b>

<h2>Parts List</h2>

<ul>
  <li><strong>Arduino Uno</strong>
    <ul>
      <li>Manufacturer: Arduino</li>
      <li>Specifications: ATmega328P, 16MHz, 5V, 32KB Flash</li>
      <li><a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/ref=sr_1_1?th=1">Arduino Datasheet</a></li>
      <li>Supplier: Amazon</li>
    </ul>
  </li>
  <li><strong>LCD Screen</strong>
    <ul>
      <li>Manufacturer: Soldered</li>
      <li>Specifications: 16x2 characters, 3.3V, HD44780 Controller</li>
      <li><a href="https://www.mouser.com/ProductDetail/Soldered/333171?qs=QpmGXVUTftF%2F5vBtqVXjsQ%3D%3D">LCD Datasheet</a></li>
      <li>Supplier: Mouser</li>
    </ul>
  </li>
  <li><strong>I2C Backpack Module for LCD</strong>
   <ul>
     <li>Manufacturer: Comimark</li>
     <li>Specifications: 5V, I2C Interface, PCF8574T IC</li>
     <li><a href="https://www.amazon.com/Comimark-PCF8574-PCF8574T-Expander-Raspberry/dp/B07X3KWQZ7/ref=sr_1_4">Datasheet</a></li>
     <li>Supplier: Amazon</li>
   </ul>
  </li>
  <li><strong>Potentiometer</strong>
    <ul>
      <li>Manufacturer: Flutesan</li>
      <li>Specifications: 10kΩ, Linear Taper, 1/4W, Rotary, 3-pin</li>
      <li><a href="https://www.amazon.com/Potentiometer-Breadboard-Resistors-Assortment-Compatible/dp/B09G9TBY38/ref=sr_1_17_sspa?th=1">Potentiometer Datasheet</a></li>
      <li>Supplier: Amazon</li>
    </ul>
  </li>
  <li><strong>Pushbutton x 4</strong>
    <ul>
      <li>Manufacturer: Wurth Electronik</li>
      <li>Specifications: Momentary, SPST, 50mA at 12V DC, Operating Force: 160gf</li>
      <li><a href="https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/430182043816/5209017">Pushbutton Datasheet</a></li>
      <li>Supplier: DigiKey</li>
    </ul>
  </li>
  <li><strong>Piezo Buzzer</strong>
    <ul>
      <li>Manufacturer: Micro Traders</li>
      <li>Specifications: BI588W, 5V, 2kHz, Passive</li>
      <li><a href="https://www.amazon.com/Micro-Traders-Electromagnetic-Loudspeakers-BI588W/dp/B0CXS43G9N/ref=sr_1_19">Piezo Datasheet</a></li>
      <li>Supplier: Amazon</li>
    </ul>
  </li>
</ul>

<h2>Schematic:</h2>

<img src="https://github.com/user-attachments/assets/9280c0fb-1601-4e2c-9b2b-81215b28f4d5"/>
<br />
<br />
