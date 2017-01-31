1. First plan for elevator: Frame was foam core, elevator was spool on wooden
dowel, and cord ran  around a pulley at the top and bottom:
![](images/spoolPulley.jpg)

cord was pulled by a motor attached to tin can around which the cord was
wound:
![](images/motorAndDrum.jpg)

support structure, showing pulleys of chair casters with corks on which the 
cord ran:
![Frame to hold elevator mechanism](images/spoolMount.jpg)


Tried various sensors:

Laser pointer and LDR
IR Proximity
2 different mechanical limit switches


Problem: Terribly unstable, sensors almost never activated

2. Second plan: decided to use mechanism I had harvested from a printer. Since
the mechanism was attached to a metal dowel, it always moved exactly in the
same line. I figured this would help my sensors sense more reliably.

2.1. Test motor by hooking up directly to 5V and GND from Arduino. It worked.

2.2. See if I can slow down the motor using analogWrite(). Need a transistor. 

By trial and error I discoverd that the slowest I could go was 220!

2.3. To avoid running into the end I added a switch and the necessary
[code](code/testMotorWithSwitch/testMotorWithSwitch.ino)

2.4. Build a frame and attach first sensor. Use analogReadSerial example to make
sure reading changes properly. Discovered I needed a tube to block ambient light.

2.5. discovered motor has to move really slowly or sensor reading isn't caught!
added serial.println() in order to catch that

discovered light went through gaps in mechamism so had to add a solid block.
now can go faster. also made mistakes in code. finally 
[code](code/testMotorWithLightSensor/testMotorWithLightSensor.ino)




Lessons learned:

1. Don't make it bigger than wherever you plan to store it, or make it so you
can take it apart

2. don't overthink - start building quickly

3. don't ever put electronics underneath or in a covered area - you will need
easy access

4. Arduino takes awhile to respond. 
	- Either make motion really slow 
		or make sure sensor is activated for a long time
	- Make sure sensor isn't too close to the end so if it keeps moving a bit
		nothing breaks
