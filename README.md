# D1 Nano

This is a simple project of designs for a D1 Nano, a [D1 Mini](https://www.wemos.cc/en/latest/d1/d1_mini.html) replacement with a smaller size and compatible with ESP32 too!
While I don't have a shop myself, I give the necessary files for making your own free of charge, so feel free to printing your own PCB with your manufacture of choice.

## Advantages

 - Smaller size compared to the D1 Mini
 - All GPIO available with its respective labels
 - Just a few of components to be used
 - Can be powered by 3.3V using 3.3V Test point, or up to 12V by using the 5V Test point (5V is recommended thought)
 - Bigger GPIOs pads compared to the raw MCU
 - Easy to assemble

## Disadvantages

 - Not compatible with breadboards, all GPIOs in use must be soldered in your project
 - [External serial programmer](https://aliexpress.com/item/32842026979.html) must be used
 - No USB connectivity, nor powering by USB

## Assembling

Note: Every component, including the ESP32, can be hand soldered. The GND pad at the back of the ESP32 is not necessary to be soldered.

 0. Download the *Garber.zip* file for your board in [Releases](https://github.com/JPZV/D1-Nano/releases/latest) and send it to your PCB manufacturer (like PCBWay)
 1. Any resistor marked by R* (R1, R2, R3, etc.) has to be filled with a **1206 10K SMD resistor**.
 2. Any capacitor marked by C* (C1, C2, C3, etc.) hast to be filled with a **1206 100nF SMD capacitor** (also named as **1206 0.1uF SMD capacitor**)
 3. Both push buttons are **3x6x2.5mm SMD SPST**.
 4.  The regulator (generally marked as **U2**) is an **AMS1117-3.3**.
 5. You can use any type of headers connector for the serial connection, even in any direction that you want. Even you can just not solder anything on it and just use four Male Jumpers wires when you want to flash without soldering and removing them when you finish.
 6. And, for the main MCU, just use the ESP that you want, just be sure to download, buy and assemble the right board (i.e. Use the ESP32 Garber file if you want an ESP32 dev Board). Keep in mind that ESP8266 is also named as ESP12. This board was tested with an ESP12-F and a ESP32-D. The ESP32 Wrover may work but I cannot guarantee it

## Flashing

Note: An [External serial programmer](https://aliexpress.com/item/32842026979.html) is needed

 1. Connect the Serial Programmer to the serial header using Jump Wires.
     a. Programmer 5V -> Board 5V
     b. Programmer TX -> Board RX
     c. Programmer RX -> Board TX
     d. Programmer GND -> Board GND
 2. Connect the programmer to your computer
 3. Press and hold the **Reset** button.
 4. Then, press the **Boot** button.
 5. Next, release the **Reset** button while holding the **Boot** button.
 6. Finally, release the **Boot** button. In some ESP32 you have to maintain the **Boot** button pressed while flashing. If you cannot flash your program, then try everything again from step 1 but don't release the **Boot** button until everything is correctly flashed.
 7. Start the Flash process in your program (VS Code, Arduino, ESPHome, Online flasher, etc.) and wait until it finishes.
 8. After it finishes correctly, do a single press in the **Reset** button.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

This project uses [MIT license](/LICENSE). This means that you can do whatever you want with this project. You can even make your own board and sell it without needing to give me a commission. But, if you want, you always can [buy me a Coffe](https://ko-fi.com/jpzv5) :)