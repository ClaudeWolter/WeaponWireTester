# WeaponWireTester
ESP32 based weapon / wire tester for fencing.
This is an accurate tester for fencing body cords and weapons.
The idea is to have a very intuitive  operation (e.g. no buttons, the devices recognizes the measuring mode) and highly accurate measurement that recognizes even the smallest (intermittent problems.
Currently the devices is capable of testing body wires and all types of weapons (foil, sabre and epee). Continuity testing for lamé is still work in progress.

# Overview:

![image](https://github.com/user-attachments/assets/49b0fbee-1a46-4eb2-9e2e-ef7cf60c51a1)


One end of the body wire (the side normally plugged into the enrouleur) is plugged into the right side of the tester, the other side (the one that is normally plugged into the weapon) is plugged into the left side of the tester. 
There is a small hole in the box to accomodate for the saftey clip of foil or sabre body cord plugs. On one side of the box, a little piece of lamé can be used to attach the crocoile clip.


![image](https://github.com/user-attachments/assets/b53730c7-0f4e-4a38-8e9d-456210d586d0)
The device is powered by USB-C (e.g. using a powerbank or a USB power adaptor).


# Operation:
The device tries to predict the intention of the user: After power on, the device is in waiting mode until something in the connections changes. E.g. as soon as a body wire is plugged-in and at least one connection between the 2 plugs is detected, the tester switches to wire testing mode. Or if the body wire is plugged in the device on one side and a weapon on the other end, the device will detect this and switch to weapon check mode.
## Wire testing
The following convention is used:
* A green full line means a correct connection of less than 3 Ohms.
* A yellow full line means a correct connection between 3 and 5 Ohms.
* A red full line means a correct connection between 5 and 10 Ohms. This is theoretically out of spec but may still work in some circumstances.
* A red dotted line means a broken connection (more than 10 Ohms).
* A blue line indicates an uninteded short circuit between 2 wires. (E.g. when 2 pins are swapped)

The testing is done in 2 phases:
### Quick Check
First a quick check is performed to indicate if all connection are potenctially correct. If there are broken wires, or wires have been swapped, or there are short circuits, the error is clearly indicated in an animation from right to left (or bottom to top). Once all 3 wires are good, the devices switches to accurate resistance testing.

### Accurate resistance checking
In this phase accurate resistance measurements are performed and the colors indicate the resistance range (from good (green) to bad (red)). During this phase, wigle the connectors, the wires, ... to verify that all connections are really stable. Even the slightest interruption will be detected and indicated for a few seconds.

## Weapon testing
### Foil & Sabre
When a sabre or foil is plugged in, this is detected by the device (because the center and 20mm pin are connected). In rest, no lights should go on. When the point is pressed, or even a small interruption in the 2 wires connecting the weapon occurs, the white light will switch on for a few seconds. When the point is pressed down on the lamé, a green ligth is switched on.

### Epee
When the epee is plugged in, and a hit is made, the devices switches to epee test mode. When the point is pressed down, the green light is switched on. Shorts between any of the wires are indicated in blue lights. 


# Hardware of the tester
The tester consists of a 3D printed enclosure (see). I use brass inserts (M2 for the PCB and M6 to fix the piece of lamé. The display is made from a 5x5 WS2812B led matrix, fixed to the top pannel.
The main PCB is the same as for the [3-weapon scoring device](https://github.com/pietwauters/esp32_scoring_device_hardware)

![image](https://github.com/user-attachments/assets/35de2eb8-d56a-4edc-a73d-227cd0f82c77)

![image](https://github.com/user-attachments/assets/d95e0430-76b3-4548-81e5-733bd35f0fec)
