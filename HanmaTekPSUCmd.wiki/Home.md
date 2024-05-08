This is my Wiki for this project and information I share about what I learn from this HM310P power supply.

# Introduction HanmaTek HM 3015P my lab power supply

My decades old linear power supply went dead on me in Mar 2020 a replacement is need. It had three DC power output, but I use mostly only 2 outlet. I think of getting a smart power supply that I can program it for varies of project with either a press of a bottom, or call a program to control the output instead of having to set the dials for the project and occasionally I will made mistake and fried some circuits.

I ended up land on this HanmaTek HM-310P - a 30V 10A power supply, I have to get two to replace my original. It can be controlled through USB, but the software that come with it does not meet my need. But lucky it provide a simple doc that disclose it is using MODBUS/Serial (through FDTI USB) to control it, so creating a program for it become this project. But the document's information is highly limited.

I also later discover, the power supply has a undocumented feature that you can set varies of parameters from its interface.

What I found from its application was the setting files, that expose some additional register addresses, but then there are features that I am not able to figure out how I can set them, such as turn on/off of OVP/OCP, I can only set them, but not to enable them.

# Hidden Menu
There is a hidden to set varies features, its not documented at all.  Some I can understand, but a lot of them remain mystical for me.  To enter the hidden menu, trun the power supply's power off (Orange button).  Now press the power ON/OFF (small white button) and turn the power supply on (Orange), do not release the white button until you see "Addr" shows up.

Once you see "Addr" 001, you are in this menu.  Press White Power Button will cycle its menu selection.  While cycling, you should notice that M1 to M6 may lighted up, that mostly meant you can press it to change the value.

Seems the only way to exit the menu is to power the unit off (Orange).  Values that set do seem retains.

| Show| type|Def| Description|
|---|---|--|--|
Addr| int | 001| Device ID 
Beep| On/Off | Off|Buzzer on/off
O.U.R. |On/Off |Off| Supply on, Output on/off setting <p>(On - on, Off- Off, On/Off - last state, out=??on with pull??)/[it is the default state in which the outputs of the power supply should turn on at the press of the mechanical button (XFalko)]
PUL- |On/Off Val| OFF/0.500 | ??
AC.F | 50/60 |50| AC cycle Hz??  If I set to 60 in US, the volt it show/measure is higher 32V becomes 33.2V
C.Err|On/Off | ON |??
C.crc | ON/Off |ON|  firmware controls for the Serial/USB port
S. F.| ON/Off | ON| ??
UoAo|Val/Val| 003/003|  M1/M2 up/down of 1st, M3/M4 up/down of 2nd
otp?? 0tp ??| List val | 070 | Cycleing 070,80,90,100,110,120,130,140, OFF
-S- | On/Off | ON | ????



# MODBUS
My collection of its power supply's [[Registers|Registers]].

