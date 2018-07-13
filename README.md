# Character-Generator

Created by Aditya Jain 

This is the Dot Matrix Character Generator Project. Using a PIC16f877A, a 16K EEPROM (28C16), a 3 to 8 decoder (74ls138), a PLD (GAL22V10), a dot matrix, and a matrix keypad, this project alllows the user to press a key on the keypad and make it appear on the dot matrix display. The Character Generator Schematic.pdf contains a schematic of the entire project and the wiring that was done. The Character Generator PLD code.PLD contains the pld code for the GAL22V10 and was obtained using karnaugh maps and boolean logic. 

The PLD serves two purposes. Four of its ouputs are a function of the keypad input and 5 of the ouputs continously cycle through the numbers 0 - 24 in binary. When the user presses a key on the keypad, the respective input on the PLD turns high and the four ouputs return a specific binary value. This points to a specific location in the EEPROM, which acts like a lookup table for the values the dot matrix needs to display the character. The numbers being cycled through by the PLD allow the correct leds to turn on one by one at a very high speed, giving the illusion that all the LEDs are on at once in a phenomenon known as persistence of vision. 5 of the ouputs of the EEPROM connect directly to the dot matrix, while 3 of them connect to the 3 to 8 decoder and specify which row of the matrix is activated. 

In order to program the EEPROM with the correct values, I created an Excel macro (Dot-Matrix-Character-Generator-Final.xlsm) to produce the hex values. This program allows the user to turn on the respective leds with the interactive display and immediately produce a hex file that can be directly downloaded to the chip. Character Generator EEPROM.hex is an example of this file.
