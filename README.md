---
description: TBD
title: TBD
keywords:
- XIAO
image: TBD
slug: xiao matrix
last_update:
  date: 8-10-2023
  author: Stephen Lo
---

<p style={{textAlign: 'center'}}><img src="https://raw.githubusercontent.com/Longan-Labs/XIAO_MATRIX_RES/main/images/1-6x10-RGB-MATRIX-for-XIAO-45font.jpg" alt="pir" width={600} height="auto" /></p>

Introducing the "6x10 RGB-MATRIX for XIAO" - a dazzling addition to the XIAO product series by Seeed Studio. The XIAO series, where "XIAO" translates to "small" or "little", represents the pinnacle of compact design with its development boards that are as tiny as a fingernail. These boards have showcased Seeed Studio's dedication to offering clear, easy-to-understand, and versatile solutions for developers. Now, with the 6x10 RGB-MATRIX, you have the power to illuminate your projects with a spectrum of colors. Comprising 60 meticulously arranged WS2812 LEDs, this matrix isn't just about aesthetics; it's a tool to bring your creative visions to life. Whether you're crafting an interactive art piece, designing a dynamic notification system, or simply wish to add a splash of color to your creations, this matrix is your canvas. Tailored for seamless integration with the XIAO main controller, its adaptability is further highlighted with the inclusion of VCC, GND, and DIN solder pads, ensuring flexibility across a multitude of scenarios.
<p style={{textAlign: 'center'}}><a href="https://www.seeedstudio.com/-Grove-VOC-and-eCO2-Gas-Sensor-(SGP30)-p-3071.html" target="_blank"><img src="https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/300px-Get_One_Now_Banner-ragular.png" /></a></p>

## Features

- 60 WS2812 LEDs: Arranged in a 6x10 grid, these LEDs are perfect for creating vibrant displays.
- Compact Design: Each LED is just 10mm x 10mm, offering a high-density display without taking up much space.
- Versatile Connection: While it's designed for the XIAO main controller, we've also included VCC, GND, and DIN solder pads for broader applications.
- RGB Capabilities: Each LED can display a wide range of colors, giving you the freedom to create dynamic and colorful displays.

## Specification

- LED Type: WS2812
- Number of LEDs: 60
- Arrangement: 6 rows x 10 columns
- LED Size: 10mm x 10mm
- Connection Port for XIAO: D0
- Additional Pads: VCC, GND, DIN, DOUT

## Applications

- Interactive Displays: Use the LED matrix for dynamic visual feedback in your projects.
- Notifications: Create colorful notifications or alerts for your devices.
- Art Installations: Incorporate the LED matrix into art pieces for a modern touch.
- Wearable Tech: Integrate into clothing or accessories for a futuristic look.
- Gaming: Enhance gaming experiences with vibrant visual effects.
- General Lighting: Use for ambient lighting or mood-setting in various environments.


## Getting Started


Welcome to the quick start guide for the 6x10 RGB-MATRIX for XIAO. This guide aims to help you set up and get started with your new LED matrix expansion board in conjunction with the XIAO RP2040 main controller.

### 1. Soldering the Headers:
Upon receiving your product, some soldering will be required. We've provided two pin headers with the package. You'll need to solder these headers onto the expansion board. 
*Refer to the image provided in the documentation for a visual guide.*

### 2. Connecting the Expansion Board:
Once the soldering is complete, you can proceed to connect the expansion board to the XIAO RP2040 main controller.
*Again, refer to the accompanying image in the documentation for clarity.*

### 3. Connecting to Your Computer:
For programming the XIAO RP2040, you'll need a TYPE-C USB data cable. Connect one end to the XIAO RP2040 and the other to your computer. For a detailed guide on programming the XIAO RP2040, please refer to this [documentation](https://wiki.seeedstudio.com/XIAO-RP2040/).

### 4. Installing the WS2812 Library:
Before you can start programming the LEDs, you'll need a specific library for the RP2040. Download the WS2812 library for RP2040 from this [GitHub link](https://github.com/MrYsLab/NeoPixelConnect). Once downloaded, install the library in your programming environment.

### 5. Programming the LEDs:
Open the `fill_demo` example from the library you just installed. However, you'll need to make some modifications to the code to get it working for our setup. Here's the modified code:

```cpp
#include <NeoPixelConnect.h>
#define MAXIMUM_NUM_NEOPIXELS 60

NeoPixelConnect p(26, MAXIMUM_NUM_NEOPIXELS, pio0, 0);

void setup(){}

void loop(){
    p.neoPixelFill(10, 0, 0, true);
    delay(1000);
    p.neoPixelClear(true);
    delay(1000);

    p.neoPixelFill(0, 10, 0, true);
    delay(1000);
    p.neoPixelClear(true);
    delay(1000);

    p.neoPixelFill(0, 0, 10, true);
    delay(1000);
    p.neoPixelClear(true);
    delay(1000);
}
```

Upload the above code to your XIAO RP2040. Once uploaded, you should observe the LEDs on the matrix cycling through red, green, and blue colors.

Congratulations! You've successfully set up and tested the 6x10 RGB-MATRIX for XIAO. Now, it's time to dive into more exciting projects and explore the full potential of this product.

## Schematic Online Viewer

<div className="altium-ecad-viewer" data-project-src="https://github.com/Longan-Labs/D7S_SENSOR_RES/raw/main/D7S%20Vibration%20Sensor.zip" style={{borderRadius: '0px 0px 4px 4px', height: 500, borderStyle: 'solid', borderWidth: 1, borderColor: 'rgb(241, 241, 241)', overflow: 'hidden', maxWidth: 1280, maxHeight: 700, boxSizing: 'border-box'}}>
</div>

## FAQ

- Q1: Do I need to solder anything when I receive the product?
- A1: If you intend to use the board in conjunction with the XIAO main controller, you'll need to solder the provided pin headers. However, if you're using the board in a different setup, soldering might not be necessary.

- Q2: Which XIAO main controller is this matrix compatible with?
- A2: While the matrix is designed to be compatible with various XIAO main controllers, the provided guide uses the XIAO RP2040 as an example.

- Q3: How do I power the 6x10 RGB-MATRIX?
- A3: The matrix can be powered through the XIAO's 5V supply or directly via the VCC solder pad with a 5V source.

- Q4: The LEDs aren't lighting up. What should I do?
- A4: Ensure that your soldering is done correctly, the matrix is properly connected to the XIAO main controller, and the correct code has been uploaded. If issues persist, refer to the official documentation or contact Seeed Studio support.

- Q5: Can I integrate this matrix into wearable tech or clothing?
- A5: Given its compact design, the 6x10 RGB-MATRIX can be integrated into various projects, including wearable tech. However, ensure that the connections are secure and the matrix is protected from excessive wear and tear.

- Q6: Can I chain multiple expansion boards together?
- A6: Yes, you can. However, some soldering will be required. You'll need to solder the DOUT of the preceding board to the DIN of the next board, and also connect the VCC and GND solder pads together.

## Resources

- **[Zip]** [Eagle file](https://github.com/stephen1874/CAN_DEV_XIAO_RES/raw/main/CAN_DEV_XIAO.zip)
- **[PDF]** [Datasheet - MCP2515](https://www.mouser.com/datasheet/2/268/MCP2515-Stand-Alone-CAN-Controller-with-SPI-200018-708845.pdf)
- **[PDF]** [Datasheet - SN65HVD230](https://www.mouser.com/datasheet/2/268/20001667G-1115479.pdf)
- **[GITHUB]** [MCP_CAN Library](https://github.com/Longan-Labs/Aruino_CAN_BUS_MCP2515)

## Tech Support
If you have any technical issue.  submit the issue into our [forum](https://forum.seeedstudio.com/).