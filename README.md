# Introduction
## What is µGUI?
µGUI is a free and open source graphic library for embedded systems. It is platform-independent
and can be easily ported to almost any microcontroller system. As long as the display is capable
of showing graphics, µGUI is not restricted to a certain display technology. Therefore, display
technologies such as LCD, TFT, E-Paper, LED or OLED are supported. The whole module
consists of three files: **ugui.c**, **ugui.h** and **ugui_config.h**.

## Fork features
This fork of µGUI introduces backend-specific user data storage to allow graphics backends to pass context (e.g., hardware driver instances) to the pset (draw pixel) callback without relying on global variables.

Changes made:
* Added void* user_data field to UG_GUI struct
* Added API functions to fetch and set user context when needed

```
void  UG_SetUserData(UG_GUI* gui, void* data);
void* UG_GetUserData(UG_GUI* gui);
```

## µGUI Features
* µGUI supports any color, grayscale or monochrome display
* µGUI supports any display resolution
* µGUI supports multiple different displays
* µGUI supports any touch screen technology (e.g. AR, PCAP)
* µGUI supports windows and objects (e.g. button, textbox)
* µGUI supports platform-specific hardware acceleration
* 16 different fonts available
* cyrillic fonts supported
* TrueType font converter available ([https://github.com/AriZuu](https://github.com/AriZuu))
* integrated and free scalable system console
* basic geometric functions (e.g. line, circle, frame etc.)
* can be easily ported to almost any microcontroller system
* no risky dynamic memory allocation required

## µGUI Requirements
µGUI is platform-independent, so there is no need to use a certain embedded system. In order to
use µGUI, only two requirements are necessary:
* a C-function which is able to control pixels of the target display.
* integer types for the target platform have to be adjusted in ugui_config.h.
