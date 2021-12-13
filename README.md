
# EnderLoop
This supports around a 110x200xinfinity bed size.

[Here](https://www.youtube.com/watch?v=L337KpcwrPk&feature=youtu.be)'s a great video with Adam at PowerBelt3D discussing the EnderLoop.

### Donations
If you find this project helpful and want to send me a cup of coffee, feel free to use this button

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate?business=MDG4UT7U4YFHJ&item_name=EnderLoop+tips&currency_code=USD)

&nbsp; 
&nbsp;  
&nbsp;  
**What's in this project:**

#### Pictures
I've attached a few pictures. Models in the printer pictures should mirror what is in the latest source files. Any differences should be minimal and are usually just that I'm running a slightly older version of the model to save on plastic waste. I've also included some test print pics to demonstrate the quality of what I'm getting off of the EnderLoop. In the pictures with two benchies, the black one is off of the belt printer whereas the white one is from a CR-6 SE as a comparison point.

#### Models
Not all of these models are required. I have included a list of what you'll need to print out and how many of each.

#### Firmware
The firmware will need to be flashed to the printer before you attempt to use it. I've included information on this in the instructions, but I've included my latest build of the firmware as well as the source in case you feel like modifying it. If you notice any issues feel free to open an issue or a PR on Github.

#### BlackBelt Cura Config
This is the configuration for the slicer. I've also included a couple snapshots in the pictures folder of what I'm using for settings on my printer currently, but keep in mind that any number of variables could change those for you (material, printer "quirks", etc.).

#### Test Models
Some test models for verifying the printer (esteps, angle, and long print adhesion). Note that the long print, as you'd probably expect, uses a large amount of material so, if you want to print that, I'd dial in smaller prints first.

### Versions
Check under the releases tab for stable snapshotted versions of this project. You can always use what is in the master branch, but since it is fluctuating with new work, there may be incorrect information or incompatible parts/software (though I try to keep everything in sync).

## Note
This is still a work in progress and you will most definitely find issues. Currently, I've identified a couple outstanding problems in my build:
1. Adhesion. I'm just gonna say outright that this isn't terrible adhesion. It's just not as good as I like it. It really depends on the model height and surface area touching the belt. You can improve the adhesion slightly by "scuffing" the surface of the belt with sandpaper.
2. Slight angle on some parts. I believe this has to do with esteps or cooling.

Most of the remaining issues are fairly minor and should either be small model updates or software tweaks.

If you experience any issues, they are most likely a result of bed leveling. I learned this the hard way so certainly check this first. Bed leveling a belt printer is trickier than with a "normal" printer and can cause some strange issues (adhesion, angled prints, head collisions, etc.)

Lastly, I'll note, and this is less of an issue and more of a limitation, but this will print slower than a normal printer due to the lead screw being used as the "de facto Y axis".

### Parts

#### Printed Parts
* 2 - AngledSupport
* 2 - BedStandV2
* 2 - BeltSlide
* 1 - EndSensorHolder
* 2 - GantryBraceBottom
* 1 - GantryBraceHolderLeft
* 1 - GantryBraceHolderRight
* 2 - GantryBraceTop
* 1 - LcdHolder
* 1 - LeftBeltClip
* 1 - ModifiedMotorHolder
* 1 - PartCoolerVent
* 1 - RightBeltClip
* 2 - Updated45ZHolder
* 2 - UpdatedAxle or UpdatedAxleCrowned or UpdatedAxleSteelRod
* 4 - UpdatedYIdler
* 2 - YExtension
* 2 - YExtensionClamp
* 11 - YExtensionSupport

##### Optional

1 - Scraper

###### Extension rollers
* 2 or 3 - UpdatedAxle
* 4 or 6 - UpdatedYIdler
* 2 - Yextension
* 8 - YExtensionSupport

#### Purchased Parts
##### Belt
Currently there are 3 options (there may be a 4th option when Creality's CR-30 belt is officially released):
1. Buy a custom belt. There are some sites that are willing to sell a custom belt. I believe BuildTak is willing to custom make a belt, however the price is fairly steep (based on my research on the WhiteKnight printer).
2. DIY. I'll include a section here on how to make a belt yourself should you want to. Note that it's going to take some patience to get a clean surface and the performance (adhesion and ability of the roller to grip the belt) will be worse than option 3. The price point for this option is also going to be about the same as option 3.
3. [POWERBELT3D Belt](https://powerbelt3d.com/product/formula32-conveyor-belt-for-enderloop/). I've reached out to Adam at PowerBelt and he was willing to list a custom belt that he has been working on that is specifically designed for the EnderLoop on his store. This is what I use right now and has pretty good characteristics. A couple of notes from the PowerBelt folks on this:
	* For PLA, we recommend a bed temperature of 60-70C.  
    * For PETG and TPU, they recommend a bed temperature of 70-80C. PETG tends to stick  _very_  well to the Polyester top layer, and might rip the material. They also recommend applying glue stick to the conveyor belt as a release agent to prevent this. If tearing still occurs, increasing the speed of outer contour that contacts the conveyor belt may help.

#####  Timing Belt
You have a few options. My recommendation would be to purchase https://www.amazon.com/gp/product/B081GYFQM3/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1
These are a little over 8mm wide. You'll note that this is wider than standard 2GT time belts (typically 6mm).
This helps it get better traction.
If you are looking to save a few bucks, you should also be able to use the extra timing belt in the Ender 3 
kit you don't need (for the original y axis). I would recommend looking up videos on joining timing belts, 
but you should be able to cut each end in the middle of a tooth (keeping note of how long you want the loop), 
rough up the back of the belt (smooth side) with sand paper, and glueing them together with a piece of 
cloth or ribbon on the roughed up side for extra adhesion support. If you find that this isn't enough to hold the belt together, 
you can try to use braided fishing line (https://www.amazon.com/gp/product/B076CMSC63/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1) 
to stitch the adhered ends together.

#####  Belt Motor
The Y motor on the Ender 3 simply doesn't have enough torque to be able to turn the belt.
I ended up purchasing https://www.amazon.com/gp/product/B07PS4BMSN/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1.
It is a Nema 17 stepper motor that draws less than 2 Amps (this is the max that the drivers on the Ender 3, regardless of version, will support).
That stepper motor I linked also coincidentally has an extra cable with it. You will either need this, 
another long stepper cable, or to make your own cable 
(https://www.amazon.com/gp/product/B077LYP4T9/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1). This is to accomodate the longer distance to the 
original Z motor which mounts at the back of the printer now, instead of the middle.
##### Pulley
Since you need to install a new motor, you will also need a new pulley for the belt motor. I used https://www.amazon.com/gp/product/B07BT6N12L/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1
#####  Springs
You will need better springs for the bed than the Ender 3 comes with. I ended up buying this assortment https://www.amazon.com/gp/product/B07V6YCYP5/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1
##### "Grippy" Paint
You will also need flex seal or another suitably "grippy" paint on coating to put on the axle.
##### Lubricant
You will need a lubricant for all of the roller ends. I always use Super Lube.

##### Steel Rods - Optional
I'm listing this here even though it is optional because I **highly** recommend this. These are for the rollers to ensure they don't flex inward. You can make this work without them, but the purely 3d printed one's can't continually handle the stress of sitting without spinning with the belt tensioned on them. With that in mind, you'll want "Tight-Tolerance Oil-Hardening O1 Tool Steel Rod, 0.3020" Diameter, 3 Feet Long" from https://www.mcmaster.com/steel-rods/tight-tolerance-multipurpose-oil-hardening-o1-tool-steel-rods/.

##### Fasteners
* T Nuts - I would recommend buying an assortment pack like https://www.amazon.com/gp/product/B07FPLZXTF/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1
although you mainly need M3 sized parts (and the Ender 3 kit comes with a couple extra M4 T nuts in case you go that route).
* M3 washers to use as spacers for the hotend. You shouldn't need more than 4.
* Assorted M3/M4 screws, mostly M3 8mm. I would recommend buying an assortment to slot in. 
Most of it is fairly flexible in what you use. Most holes in the parts I designed are for M3 screws, but you 
can enlarge the holes in the models if you go with another screw size.
* 2 M3 20mm screws and 2 M3 nuts for attaching the hot end lower on the print head mount plate.
* 4 M5 screws for attaching the gantry to the base. I would recommend they be 40-50 mm long since they will be holding the gantry, but the length is fairly flexible.
* 2 M5 screws and 2 M5 nuts for attaching the lcd screen to the mount. I would recommend around 30 mm long, but, again, that's fairly flexible. 

#### Tools
I've tried to make this install as "tool-less" as possible to make it accessible. That said, I've determined that in order to make this as functional as possible, there are a couple tools you'll need (or you can go to your local metal/machine shop to have done for you). 
* Drill with titanium bits (or another bit that can drill steel)
* Dremel with a diamond coated cutting bit (or another bit that can cut steel)

#### Optional:
* You may want to consider purchasing a few nylon washers to go above the springs, but below the heated bed. This will prevent damage to the heated bed from the metal spring. This is more of an Ender 3 design upgrade than an EnderLoop mod component, but I think it's worth mentioning, especially if you replace the default springs with stronger ones.
* I sadly managed to break endstops while I was tinkering with design and assembly. If you find yourself in a similar predicament,
these work as replacements https://www.amazon.com/gp/product/B08G7Y5C63/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1
* I also unfortunately managed to fry my mainboard (specifically a driver) while I was tinkering and ended up replacing it with https://www.amazon.com/gp/product/B07TYFJ924/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1. These boards are fantastic because the drivers on them are INCREDIBLY quiet. The loudest part on the printer after installing one of these becomes the fans.
* If your mainboard is V1.1.5, you will need either an Arduino or a USBTiny (https://www.amazon.com/gp/product/B07S9BX98K/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8&psc=1)

#### DIY Belt Instructions
 In order to keep this lower cost, the backing is steel shim, which I taped into a belt using kapton tape.
I then coated the hole belt in kapton tape. Your other options are PET tape or PEI sheets with an adhesive coating between the sheet and the steel shim. 
Steel shim link: https://www.mcmaster.com/steel-shim-stock/shim-stock-6/
Instructions on sizing this are further down in the assembly information.


### Firmware
You will note that there are a few combinations of mainboards/drivers that ender 3's can come with:
##### Motherboards:
* V1.1.5
* V4.2.2
* V4.2.7

##### Drivers:
* HR4988
* A4988
* TMC2208
* TMC2225

The precompiled firmware is meant for V4.2.7 and TMC2225 drivers (should also work with TMC2208 drivers). If you are using any other board/driver combination, 
you will need to edit the firmware I provided. 
Best I can tell, it seems that V1.1.5 comes with A4988, V4.2.7 comes with TMC2208 or TMC2225, and V4.2.2 can come with any 
of the drivers listed.
V4.2.7 and V4.2.2 are simple enough to program. Simply place a compiled binary on a microsd card and insert into the printer. 
When you turn it on it will flash the printer. If it complains about mismatched EEPROM, just ignore it and update the 
EEPROM in the menu on the printer (lots of examples on the internet). If you have a V1.1.5, you will need to flash the firmware using
and Arduino or a USBTiny (https://www.amazon.com/gp/product/B07S9BX98K/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8&psc=1).
Not gonna go into to many details here as there's plenty of information on flashing the firmware available online.

### Slicer
You will need to install BlackBelt Cura to do belt printing. Once installed, find the install directory (C:\Program Files\BlackBelt Cura 3.6.0\resources on Windows)
and copy/paste the Config folders I included here. This will prompt to overwrite a file, say yes. The config I included overwrites the BlackBelt default one. 
This should be fine since most people who can afford a BlackBelt probably aren't making this ;)

### Wiring
As far as wiring goes, there are a few things to keep in mind. Look at the stepper motor cable wire order in the connectors (the prebuilt connectors that come with the printer).
You'll note the middle two wires are inverted. Make sure you keep a close eye on whether a cable is supposed to have those wires
inverted or not. The motor I purchased to drive the belt did not want those wires inverted, but all the Ender 3 motors do.
One other thing to keep in mind is that all belt printers treat what we would normally consider the Y direction as Z. To 
accommodate this, you will need to plug the belt motor into the Z slot on the mainboard and the gantry motor into the Y slot on the mainboard.
You will also need to plug the gantry end stop switch into the Y slot on the mainboard. You don't need a Z end stop switch (since there is no zero on a belt). 
Everything else should be wired the same.

### Print settings
Everything was printed somewhere between a 20-30% infill except for the axles which were printed at 60% infill and the RightBeltClip which was printed at 80% infill.

You also may find the part tolerances to be too tight or too loose depending on how your printer is calibrated. You can either modify the models slightly to increase/decrease the size or use the horizontal expansion setting in Cura adjust the part prints.

### Assembly
Assembly is fairly straight forward and most of it should make sense off of the pictures. 
To start, you will need to strip down a few parts that are on the Ender 3 already. 
Most of the parts you will be taking off are on the bed. You won't need the timing belt, motor, or aluminum extrusion directly under the bed. I've attached a picture to give you an idea of most of the parts you won't need.

You will need to keep the metal plate, screws, and tightening wheels right under the bed. This metal plate is what you will attach to the BedStand model and you should be able to attach it in the same way the wheels were originally attached (same nuts and bolts).
Depending on how tight this model is to your aluminum extrusion, you can use T nuts and screws to secure the BedStand more tightly. As far as replacing the springs that come with the Ender 3, I would recommend experimenting with a few different spring tensions. I used two different varieties of spring since one side of my printer needed to be tightened down more than the other. I would also recommend putting a nylon washer on top of each spring (just under the heated bed) to prevent the spring from scraping the heated bed.

The gantry is mounted at a 45 degree angle. This is accomplished with the Updated45ZHolder and the AngledSupport files. Slide the AngledSupport on first to the aluminum extrusion base and then slide the gantry extrusion into it. Lastly, slide the ModifiedMotorHolder onto the end of the gantry extrusion and screw the Updated45ZHolder into the gantry extrusion (these screws should be the ones that come with the printer) 
and the base extrusion (these will be the longer M5 screws mentioned on the parts list). I only used two screws on the base extrusion since that seemed sufficiently sturdy.

The hot end needs to be lowered on the print head. This is where the drill with a titanium bit comes in. You will be drilling a hole to accommodate the M3 20mm screws that attaches the hot end to the print head plate. I've attached a picture of this, but basically the holes should be drilled as low as possible without reaching the point on the steel where it starts to curve. It should also be vertically aligned with the original screw holes. Once you've done this, you can mount the hot end using the M3 20mm screws and M3 nuts using 4 M3 washers (2 per screw) as spacers between the hot end and the steel print head plate. Note, these screws need to extend past the back of the steel print head plate exactly the right amount so you can install the washer. If it goes to far, the screws will grind on the aluminum extrusion when it slides left to right and you will run into problems.

Most likely the silicon sock that comes with the Ender 3 will have material that covers the brass nozzle on the hot end. You'll want to trim the silicon that covers the brass nozzle or it will hit the bed or your in progress print due to the 45 degree print angle. 
You'll also need to remove the print fan vent piece from the side of the print head and replace it with the PartCoolerVent.

The print head is mounted 90 degrees from how a standard Ender 3 is constructed. To handle this, you need to unscrew the wheels on the print head and mount the LeftBeltClip and RightBeltClip under those screws.
The X axis timing belt slides into the slots on those two parts. Note that you'll want to install the timing belt on the LeftBeltClip before you resecure the wheels.
Once that is in place, you should be able to install the print head on the aluminum extrusion and install the timing belt around the motor (like you normally would).
Lastly, you'll need to install the EndSensorHolder on the side of the aluminum extrusion that the hot end is on. Slide it as far left as you can without the print head hitting the metal support that attaches to the extrusion. This is installed using a T nut. You will need to remove the limit switch on the X axis (it's at the end of this rod under a plastic cover where the timing belt runs). This limit switch can then be screwed onto the EndSensorHolder.

Next you will add the gantry support pieces. This will involve attaching the GantryBraceHolderLeft on the left aluminum extrusion on the base and the GantryBraceHolderRight on the right aluminum extrusion on the base. This provides a socket hole on top to install the GantryBraceBottom into each of them. On top of the GantryBraceBottom you will use 8 (4 on each) to attach the GantryBraceTop's. These will then screw in to the top of the gantry using the outermost screw hole (you'll need to remove the screw that was there already) and a couple extra M5 screws you should have lying around from stripping parts off of the Ender 3.

The next step is to extend the base. You will need to install two YExtension pieces at the front of the base (towards you) using two YExtensionClamp's and 4 YExtensionSupport's. I would recommend sliding the ModifiedMotorHolder onto the left YExtension before clamping the YExtension in place.
These will be held in place using T nuts. 
You can then mount the ModifiedMotorHolder using T nuts on the left YExtension. 

Note, for all of the roller instructions that follow, you will need to apply a lubricant to the rollers where they contact the idlers.
You have 3 options for the rollers. 
1. UpdatedAxle - This is just a standard 3d printed roller.
2. UpdatedAxleCrowned - This is a 3d printed roller with crowning in the middle to keep the belt inline.
3. UpdatedAxleSteelRod - This is a 3d printed roller that you insert a steel rod into the middle of for support.

I would recommend option 3. Should you go this route, the only additional work you need to do is:
1. Cut the 3 ft steel rod into two, roughly 11in pieces (slightly longer is fine, but I wouldn't go shorter than that).
2. Insert the steel rod pieces into two UpdatedAxleSteelRod prints. If it won't go through, I'd run a drill bit of a _slightly_ larger diameter through the inside of the model to loosen the tolerance.
3. If the steel rod sticks a bit, that's fine. I used a hammer to finish the job. Having it tight is perfectly fine (and actually makes it a bit simpler to install). If it isn't tight, you'll want to apply an adhesive to keep it in place so it doesn't slide out.

No matter which of the roller options you choose, you will install one of the rollers using two UpdatedYIdler's and T nuts at the back of the printer (just behind the bed).
The next roller you'll be installing will be the one that the motor drives. The roller model itself won't be able to grip the belt as it stands. You need to coat this roller, including the teeth, in a thin coating of something "grippy". I found FlexSeal paint worked well.
Then you will need to mount this roller using two UpdatedYIdler's and T nuts at the front of the printer (between the ModifiedMotorHolder and the bed).

You then install two BeltSlide's. One goes on the back side of the print bed (on that metal plate under the bed, kind of between the tightening wheels) and one on the front side (between the other two tightening wheels).

---
###### DIY Belt Sizing
You will cut the steel shim based on the width between the two guard bumps on the rollers and the length a little longer than necessary to go around the rollers, over the bed and over the belt slides.
Note that the steel shim is super sharp when cut, but you should be able to file it down.

---

The belt (regardless of which option you chose) can then be fed under the axle, over the two BeltSlide's (inside the small teeth that hold it), under the other axle, and back over the bed.

---
###### DIY Belt Coating
You will want to tape it tight and straight (if either side is longer than the other, prints won't work well). Then run Kapton tape lengthwise over the belt to cover it for better print adhesion.
Less deformities in the tape is better as it will increase adhesion and lower model warp.

---

--- 
###### PowerBelt Belt Installation
From the folks at PowerBelt: https://youtu.be/ShYZX8OavIs 

I will also note here that it can be helpful to lightly scuff the surface of the belt with sandpaper to increase the adhesion a bit.

--- 

You will want to install the belt motor into the ModifiedMotorHolder and attach a pulley to the motor axle.
The timing belt will then go around the teeth on the axle and the pulley.
Then you can install the LcdHolder on the right YExtension using T nuts and some screws (don't recall the size on these, had a few laying around).

#### Optional
Lastly, if you want an extension with rollers for longer prints, you can print out additional YExtension's, YExtensionSupport's (4 for each extension, go on the bottom half), and UpdatedYIdler's/UpdatedAxle's (as many as you'd like really, 2 UpdatedYIdler's per UpdatedAxle).

### Sources
I went through quite a few sources online to learn enough to make this happen. I wanted to list a few to acknowledge and also for anyone who wants to learn more. In particular I wanted to mention the Infinity Ender project on Thingiverse which provided a lot of the part inspiration. I also wanted to mention the aluminum extrusion Thingiverse entry in this list. I based my y extensions off of that model.

https://www.thingiverse.com/thing:4267968

https://www.instructables.com/Turn-Your-3D-Printer-Into-a-Factory-Automatically-/

https://hackaday.io/project/114738-automatic-infinite-3d-printer/log/146614-ejecting-parts-from-workhorse-3d-printer-mk-3/discussion-122983

https://www.thingiverse.com/thing:280318

https://hackaday.io/project/114738/instructions

https://www.reddit.com/r/3Dprinting/comments/4tc1x8/part_removal_conveyor_belt_thingy_for_larger/

https://www.thingiverse.com/thing:3434404

https://forum.duet3d.com/topic/8332/modded-ender-3-conveyor-concept/2

https://blackbelt-3d.com/the-blackbelt-3d-printer/

https://www.youtube.com/watch?v=czozhy7kjwc&feature=youtu.be

### License
EnderLoop is licensed under the [Creative Commons - Attribution - Non-Commercial license](https://creativecommons.org/licenses/by-nc/4.0/).
