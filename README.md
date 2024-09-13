<h1>Digital Clock with Alarm</h1>

 ### [YouTube Demonstration](https://youtu.be/wvlziquP9fc)

<h2>Description</h2>
In this Digital Clock project, an Arduino Uno is programmed to control a functional clock system. Users can set both the current time (hours and minutes) and the alarm time through a user interface consisting of buttons. The current time is continuously displayed on a Liquid Crystal Display (LCD) with optional backlighting for better visibility. The clock is powered through a USB connection with the Arduino. When the set alarm time is reached, a piezo buzzer sounds and the clock stops. The system is programmed using the Arduino IDE and includes error handling to manage incorrect time or alarm settings.
<br />


<h2>Environments Used </h2>

- <b>EasyEDA</b>
- <b>Arduino IDE</b>

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
     <li><a href="https://www.amazon.com/Comimark-PCF8574-PCF8574T-Expander-Raspberry/dp/B07X3KWQZ7/ref=sr_1_4">I2C Backpack Datasheet</a></li>
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

<img src="https://github.com/user-attachments/assets/c259330a-3a83-4f3d-b0c7-5018a0babfdd"/>

<h2>Program walk-through:</h2>

<div style="text-align: center;">
    Libraries: <br/>
    <img src="https://github.com/user-attachments/assets/94bc0b16-e0f3-43a1-ac9f-e078b0a9011e" alt="LCD Libraries" />
    <p>These libraries are included to control an LCD connected through the I²C communication protocol. Go to Sketch > Include Library > Manage Libraries. In the Library Manager search for LiquidCrystal I2C by Frank De Brabander and install.</p>
</div>
<br />

<div style="text-align: center;">
    LCD Setup: <br/>
    <img src="https://github.com/user-attachments/assets/19bdf777-171b-4573-8991-7b41e9be3c84" alt="LCD Setup" />
    <p>The lcd object is created using the I²C address 0x27, and the LCD has 16 columns and 2 rows. Make sure to find your own LCD's address, you can do so by following this guide <a href="INSERTLINK">here</a>.</p>
</div>
<br />

<div style="text-align: center;">
    Variables: <br/>
    <img src="https://github.com/user-attachments/assets/7f61c326-1765-4296-a67d-a62e9976d37a" alt="Variables" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>starttime: Tracks when the program starts.</li>
        <li>activetime: Tracks the current runtime in seconds.</li>
        <li>prevoustime: Stores the last second when a minute passed.</li>
        <li>hours and mins: Track the current time (hours and minutes).</li>
        <li>ahours and amins: Store the alarm time (hours and minutes).</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Setup: <br/>
    <img src="https://github.com/user-attachments/assets/d5b119b8-1caf-4aaf-8808-6c45c17c53fa" alt="Setup" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>The LCD is initialized, and the backlight is turned on.</li>
        <li>Various pins are configured as inputs with internal pull-up resistors for buttons and outputs for the buzzer on pin 9.</li>
        <li>starttime is set to the current time in seconds.</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Main Loop: <br/>
    <img src="https://github.com/user-attachments/assets/9561ad46-b420-4cc2-9740-0d66af37dbe0" alt="Main Loop 1" />
    <img src="https://github.com/user-attachments/assets/bebd55b1-4f67-401c-81dd-cbc96be80223" alt="Main Loop 2" />
    <img src="https://github.com/user-attachments/assets/49f19c66-e548-4ddd-a576-e224b69109a2" alt="Main Loop 3" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>If the button on pin 8 is pressed (set low), the alarm time is set.</li>
        <li>Buttons on pin 11 and 10 are used to increment the alarm minutes (amins) and hours (ahours), respectively.</li>
        <li>When a number for hours or minutes that is less than 10 is displayed a zero is displayed before it to maintain 2 digits of information.</li>
        <li>The display is updated to show the alarm time in HH format, handling the cases where hours or minutes exceed their maximum values (23 for hours, 59 for minutes).</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Time Setting: <br/>
    <img src="https://github.com/user-attachments/assets/88a81ffc-d965-4e9f-9a59-ae3d5dfe60b5" alt="Time Setting" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>If the button on pin 13 is pressed, the current time is set.</li>
        <li>Buttons on pin 11 and 10 are again used to increment minutes (mins) and hours (hours).</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Time Update and Display: <br/>
    <img src="https://github.com/user-attachments/assets/1dd8207b-14cf-498f-a2ee-00aa546bf041" alt="Time Update 1" />
    <img src="https://github.com/user-attachments/assets/d540949c-cf09-4ce2-87cb-18bb7f570f98" alt="Time Update 2" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>activetime is updated to the current runtime in seconds since the program started.</li>
        <li>Every 60 seconds, the minutes are incremented, and prevoustime is updated.</li>
        <li>When a number for hours or minutes that is less than 10 is displayed a zero is displayed before it to maintain 2 digits of information.</li>
        <li>The hours and minutes are incremented and wrapped around their limits (23 for hours, 59 for minutes).</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Alarm Check: <br/>
    <img src="https://github.com/user-attachments/assets/102b7d0f-a215-4293-8259-8c518aba5555" alt="Alarm Check" />
    <ul style="list-style-position: inside; text-align: left; display: inline-block;">
        <li>The alarm is triggered when the current time (hours, mins) matches the alarm time (ahours, amins), provided that the minutes (amins) are non-zero.</li>
        <li>A tone is played on the buzzer on pin 9 when the alarm goes off.</li>
    </ul>
</div>
<br />

<div style="text-align: center;">
    Serial Output: <br/>
    <img src="https://github.com/user-attachments/assets/323cd5af-cad6-46e7-8f9e-4927afd53797" alt="Serial Output" />
    <p>The current minutes, hours, alarm minutes, alarm hours, and other timing variables are printed to the Serial Monitor for debugging purposes.</p>
</div>
<br />
