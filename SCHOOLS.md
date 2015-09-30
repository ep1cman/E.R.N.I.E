Using E.R.N.I.E in schools
==========================
E.R.N.I.E was designed from the very start to be used for education and therefore I have open sourced the project so any school can use and build upon it. If you wish to use E.R.N.I.E for teaching students here are a few recommendations from past experiences.

The kit can be assembled by 1-3 students. I find that two students to be the optimum amount. I would not recommend more than 3 students per group as there really isn't enough for them all to do simultaneously. The project requires around 5-7 hours to complete.

Learning Objective
------------------
As it stands E.R.N.I.E and its existing documentation aim to:
 * Teach how a line following robot works
 * Teach basic programming skills
 * Teach basic Arduino skills
 * Teach basic robot construction skills

There is also a lot of potential to widen the scope of this project. For example:
 * If your school has access to a laser cutter and time permits it, students could be allowed to watch their own kit be cut to learn about CAD/CAM.
 * The project also has the opportunity to utilise 3D printing to extend its features. It's likely this would need to be done in advance due to the time 3D printing requires, but students could be shown how 3D models are created. Then watch one start printing at the start of their session to see it complete at the end.
 * Two out of the three wheels need to have their hubs drilled out to 5mm. This can be done with a drill press set to very slow speeds due to the soft rubber material they are made of. This could be used to teach students fabrication skills.
 * Using ultra sonic sensor worksheets and examples for obstacle avoidance. *
 * For more advanced classes a PID controller could be implemented in software or hardware. *
 * The software could be written in low level C* rather than with Arduino libraries or even in Assembly
 * The Arduino and motor shield could be replaced by analogue electronics to teach basic Op-Amp theory *

\* denotes items which are in progress but I cannot guarantee when they will be complete.

License Details
===============
This project is licensed under the CERN open hardware license v1.2. This means you are free to use any of the files you find here however you see fit. There are only a few simple requirement that you must do under this license:

 * If you make any changes to the project please share them freely, under the same license.
 * Please list your changes in [CHANGES.TXT](license/CHANGES.TXT).
 * Please notify the people listed in [CONTRIB.TXT](license/CONTRIB.TXT) of your changes.
 * If you know how to use git and feel your change improve the project (e.g. fixing my spelling/grammar or updating the worksheet) please fork this repository and make a pull request of your changes.
 * If you produce any E.R.N.I.E kits (chassis or PCBs) please notify the people listed in [PRODUCT.TXT](license/PRODUCT.TXT).

If any of your e-mails fail to go through you don't need to worry about it. The reason I ask for these things is so that the people who have contributed to the project can see how it progresses and that it remains free for everyone.

Kit preparation
===============
Prior to students starting to build an E.R.N.I.E there are a few steps that need to be done in advance unless you have the time and want students to perform them. In this repository there is all file called BoM.xlsx (Bill of Materials). Said file contains a full list of what is required for the main chassis, the sensor board and the optional sonar sensor.

#### Laser cutting
The chassis can be laser cut from 3 materials each with their own pro's and con's:
 * __Acrylic__ - Looks good and is affordable but extremely brittle and easy to break.
 * __Plywood__ - Cheap, strong and can easily be modified but some people think it looks less attractive.
 * __Polycarbonate__ - More expensive than acrylic but not brittle.
I personally would recommend using plywood as it is more robust and can easily be hacked by students wanting to modify their robots.

If you do not have access to a laser cutter there are several companies who offer laser cutting services for very reasonable prices online. I have included a ready made [file](Chassis v2.1.razorlab.svg) for [Razorlab](http://www.razorlab.co.uk/). The design fits onto their P1 size sheets and will set you back ~£11.50 for a plywood E.R.N.I.E, although I am sure in bulk the price would decrease. Be sure to use 3mm thick material.

#### Wheels
Each kit needs 3 wheels, two of which need to have their hub enlarged to 5mm. This can be done very easily on a drill press running on a slow speed or by hand with a drill bit.

#### PCBs
I highly recommend getting professionally manufactured PCBs from one of the many Chinese PCB fab houses. I used [Elecrow](http://elecrow.com) and got 50 boards produced for £22.57 (45p a board!). If you would like to recreate the exact boards I got made you can simply visit [this page](http://www.elecrow.com/10pcs-2-layer-pcb-p-1175.html) and enter the following settings:
 * __Layer__ - 2
 * __PCB Thickness__ - 1.6mm
 * __Copper Weight__ - 1oz 35um
 * __PCB Size__ - 10cm Max * 10cm Max
 * __PCB Color__ - Black
 * __Suface Finish__ - Hasl (lead free)
 * __PCB Stencil__ - NO Stencil
 * __Panelizing__ - 2-5 copies
 * __Lead time__ - Shipped in 4 to 7 days
The zip file you need to attach can be found [here](src/PCB/gerbers (elecrow).zip)

#### Packaging
I find Tesco zip lock freezer bags are the perfect size for the E.R.N.I.E kit. I would advise against packing the six AA batteries with the rest of the kit to prevent them getting shorted by components.

When packing the IR LEDs and IR photodiodes be very careful not to mix them up. Either bag the two individually or use tape to keep them together and label them. The two are __VERY__ difficult to distinguish. On a side note, mobile phone cameras are an extremely good way to test if the IR LEDs are working. Most mobile cameras do not fully filter out IR light and they should appear white/blueish when illuminated.

#### Spare parts
I would highly recommend getting spares of the following components:
 * __IR LED/Photodiodes__ - Inevitably someone will solder an LED into a photodiode slot or the wrong way around. Its easier to use a fresh one than try salvage a used one.
 * __Sensor Holders__ - If these are made from acrylic they can be very easy to break if too much force is applied to them.
 * __Nuts__ - very easy to loose and you can buy them in large quantities very cheaply.

#### Software
The arduino software runs well on all major operating systems but does require administrator privileges on windows to install drivers. If the students will not be using accounts with administrator privileges (as is the case in most schools) please ensure that you plug an arduino into every USB port they might use on the PCs. Windows will then proceed to install drivers which will not need to be done again by the students.

The worksheet has been written using version 1.6.5 of the arduino IDE. With only minor changes (the library installation) it can work with much older versions. It may also be the case that future arduino IDE releases might slightly change the steps shown in the worksheet but these are unlikely to be major. If this is the case let me know and I will update the worksheet.

Students also require internet access to be able to install the adafruit motor shield v1 library, if this is not possible you will need to go ahead and pre-install the library on their machines. Instructions on doing this can be found [here](https://learn.adafruit.com/adafruit-motor-shield/library-install) (please ignore the message about v2 at the top of this page).

#### Testing
If you opt for using chinese clone arduinos and the adafruit motor shields (which dramatically decreases the cost of the kit). I would highly recommend testing the hardware before giving it to students and possibly ordering a spare of each. I have encountered some shoddy soldering on a motor shield in the past that had prevent it from working.