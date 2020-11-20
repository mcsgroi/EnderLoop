# EnderLoop
This supports around a 110x200xinfinity bed size.

I've attached a few pictures. You'll note that these were as I was assembling so some of the parts may not quite match what I've uploaded for models here. The later pictures should be more up to date. I've also included a couple of benchy pics. The pearl colored one is off of the belt printer (apologies for it only being partially printed, ran out of material part way through :) ) whereas the white one is from a CR-6 SE as a comparison point.

## Note
This is still a work in progress and you will most definitely find issues. Currently, I've identified a few outstanding problems in my build:
1. Belt surface is warped and uneven. I believe this is mostly due to poor craftsmanship on my part when I assembled it. I believe this can be resolved by simply redoing that work
2. Part is elongated a bit. I haven't been able to decide if this is caused by the belt or not. If not, I suspect the steps in the firmware need adjusted.
3. The belt is curving on the edge a bit. I think that could be minimized by redoing the belt as well. If not, this may require additional designs to update the print head and replacing the tensioner rod on the back with another axle so it's close to the bed height.

### Parts
You will need something for the belt. In order to keep this lower cost, I purchased steel shim, which I taped into a belt using kapton tape.
I then coated the hole belt in kapton tape. There are probably alternatives to this one, but this seemed like the simplest, cheapest, and most universal option.
Steel shim link: https://www.mcmaster.com/steel-shim-stock/shim-stock-6/

You will need a timing belt. You have a few options. My recommendation would be to purchase https://www.amazon.com/gp/product/B081GYFQM3/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1
These are a little over 8mm wide. You'll note that this is wider than standard 2GT time belts (typically 6mm).
This helps it get better traction.
If you are looking to save a few bucks, you should also be able to use the extra timing belt in the Ender 3 
kit you don't need (for the original y axis). I would recommend looking up videos on joining timing belts, 
but you should be able to cut each end in the middle of a tooth (keeping note of how long you want the loop), 
rough up the back of the belt (smooth side) with sand paper, and glueing them together with a piece of 
cloth or ribbon on the roughed up side for extra adhesion support. If you find that this isn't enough to hold the belt together, 
you can try to use braided fishing line (https://www.amazon.com/gp/product/B076CMSC63/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1) 
to stitch the adhered ends together.
You will need quite a few T nuts. I would recommend buying an assortment pack like https://www.amazon.com/gp/product/B07FPLZXTF/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1
although as I mentioned you mainly need M3 sized parts (and the Ender 3 kit comes with a couple extra M4 T nuts in case you go that route).
You will need a new motor for the belt. The Y motor on the Ender 3 simply doesn't have enough torque to be able to turn the belt.
I ended up purchasing https://www.amazon.com/gp/product/B07PS4BMSN/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1.
It is a Nema 17 stepper motor that draws less than 2 Amps (this is the max that the drivers on the Ender 3, regardless of version, will support).
That stepper motor I linked also coincidentally has an extra cable with it. You will either need this, 
another long stepper cable, or to make your own cable 
(https://www.amazon.com/gp/product/B077LYP4T9/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1). This is to accomodate the longer distance to the 
original Z motor which mounts at the back of the printer now, instead of the middle.
Since you need to install a new motor, you will also need a new pulley for the belt motor. I used https://www.amazon.com/gp/product/B07BT6N12L/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1
You will need better springs for the bed than the Ender 3 comes with. I ended up buying this assortment https://www.amazon.com/gp/product/B07V6YCYP5/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1
You will also need flex seal or another suitably "grippy" paint on coating to put on the axle.
Lastly, you will need a lubricant for all of the roller ends. I always use Super Lube.

Assorted M3/M4 screws, mostly M3 8mm. I would recommend buying an assortment to slot in. 
Most of it is fairly flexible in what you use. Most holes in the parts I designed are for M3 screws so you 
can enlarge the holes in the models if you go with another screw size.

#### Optional:
I sadly managed to break endstops while I was tinkering with design and assembly. If you find yourself in a similar predicament,
these work as replacements https://www.amazon.com/gp/product/B08G7Y5C63/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1
I also unfortunately managed to fry my mainboard (specifically a driver) while I was tinkering and ended up replacing it with https://www.amazon.com/gp/product/B07TYFJ924/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1
If your mainboard is V1.1.5, you will need either an Arduino or a USBTiny (https://www.amazon.com/gp/product/B07S9BX98K/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8&psc=1)


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
accomodate this, you will need to plug the belt motor into the Y slot on the mainboard and the gantry motor into the Y slot on the mainboard.
You will also need to plug the gantry end stop switch into the Y slot on the mainboard. You don't need a Z end stop switch (since there is no zero on a belt). 
Everything else should be wired the same.

### Print settings
Everything was printed somewhere between a 20-30% infill except for the TensionerRod and the RightBeltClip which were printed at 80% infill.

### Assembly
Assembly is fairly straight forward and most of it should make sense off of the pictures. 
To start, you will need to strip down a few parts that are on the Ender 3 already. 
Most of the parts you will be taking off are on the bed. You won't need the belt, motor, aluminum extrusion.
You will need to keep the metal plate, screws, and tightening wheels right under the bed. This metal plate is what you will 
attach to the BedStand model and you should be able to attach it in the same way the wheels were originally attached (same nuts and bolts).
Depending on how tight this model is to your aluminum extrusion, you can use T nuts and screws to secure the BedStand more tightly.
The gantry is mounted at a 45 degree angle. This is accomplished with the Updated45ZHolder and the AngledSupport files. Slide the
AngledSupport on first to the aluminum extrusion base and then slide the gantry extrusion into it. Lastly, slide the ModifiedMotorHolder
onto the end of the gantry extrusion and screw the Updated45ZHolder into the gantry extrusion (these screws should be the ones that come with the printer) 
and the base extrusion (don't recall the size on these screws, had a few laying around)
(I only used two screws on the base extrusion since that seemed sufficiently sturdy).
The print head is mounted 90 degrees from how a standard Ender 3 is constructed. To handle this, you need to unscrew the wheels 
on the print head and mount the LeftBeltClip and RightBeltClip under those screws.
The X axis timing belt slides into the slots on those two parts. Note that you'll want to install the timing belt on the LeftBeltClip before you resecure the wheels.
Once that is in place, you should be able to install the print head on the aluminum extrusion and install the timing belt around the motor (like you normally would).
Lastly, you'll need to install the EndSensorHolder on the side of the aluminum extrusion that the hot end is on. Slide it as far left as you can without the print head 
hitting the metal support that attaches to the extrusion. This is installed using a T nut.
The next step is to extend the base. You will need to install two YExtension pieces at the front of the base (towards you) using two YExtensionClamp's and 4 YExtensionSupport's.
These will be held in place using T nuts. 
You can then mount the ModifiedMotorHolder using T nuts on the YExtension. 
Note, for all of the roller instructions that follow, you will need to apply a lubricant to the rollers where they contact the idlers.
Once that is in place you will need to mount a TensionerRod using two ShortIdler's and T nuts at the back of the printer (just behind the bed).
Note, the UpdatedAxle won't be able to grip the belt as it stands. You need to coat the axle, including the teeth, in a thin coating of something "grippy". I found FlexSeal paint worked well.
Then you will need to mount an UpdatedAxle using to Y_idler's and T nuts at the front of the printer (between the ModifiedMotorHolder and the bed).
You then install two BeltSlide's. One goes on the back side of the print bed (on that metal plate under the bed, kind of between the tightening wheels) and one on the front side (between the other two tightening wheels).
You will cut the steel shim based on the width between the two guard bumps on the rollers and the length a little longer than necessary to go around the rollers, over the bed and over the belt slides.
Note that the steel shim is super sharp when cut, but you should be able to file it down.
The shim can then be fed under the UpdatedAxle, over the two BeltSlide's (inside the small teeth that hold it), under the TensionerRod, and back over the bed.
You will want to tape it tight and straight (if either side is longer than the other, prints won't work well). Then run Kapton tape lengthwise over the belt to cover it for better print adhesion.
Less deformities in the tape is better as it will increase adhesion and lower model warp (although I definitely didn't do a great job with that :) ).
You will want to install the belt motor into the ModifiedMotorHolder and attach a pulley to the motor axle.
The timing belt will then go around the teeth on the UpdatedAxle and the pulley.
Then you can install the LcdHolder on the right YExtension using T nuts and some screws (don't recall the size on these, had a few laying around).
Lastly, if you want an extension with rollers for longer prints, you can print out additional YExtension's, YExtensionSupport's (4 for each extension, go on the bottom half), and Y_idler's/UpdatedAxle's (as many as you'd like really, 2 Y_idler's per UpdatedAxle).

### Sources
I went through quite a few sources online to learn enough to make this happen. I wanted to list a few to acknowledge and also for anyone who wants to learn more. In particular I wanted to mention the Infinity Ender project on Thingiverse. The y idler and the 45 degree gantry holder (made a few modifications to this model) come from there. I also wanted to mention the aluminum extrusion Thingiverse entry in this list. I based my y extensions off of that model.
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