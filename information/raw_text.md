# Deck Content (Flat View)


## Slide 1: ETAD 130 FINAL PROJECT SPRING 2026
_intent: `hero`_

- Mark I-inspired tracked vehicle
- Differential gear learning and autonomous vehicle platform.
- A rhomboidal-hulled tracked vehicle, modeled in Autodesk Inventor,
- 3D-printed in PLA, and assembled by hand, put into motion using Arduino-based electronics
- Bogdan Mironov
- Instrutor: Dr. Benjamin Remon

## Slide 2: 01.
_intent: `pricing`_

- OVERVIEW
- The build, in 3 numbers.
- Fig. 1   The assembled prototype vs. Inspiration model (original design dated 1916)
- ETAD 130  ·  B. MIRONOV
- Overview
- 2 / 13
- DRIVETRAIN
- Differential gear
- 8
- gear components
- Bevel pinion ; motor input
- Crown gear; speed reduction
- Carrier housing ;  rotates with crown
- 2 x side gears ;  output to track shafts
- 2 x spider gears ;  the planet gears
- Cross pin; spider-gear shaft
- ELECTRONICS
- Control and power
- 7
- electronic items
- Arduino UNO microcontroller
- TB6612 stepper-motor driver
- NEMA 17 stepper motor
- Breadboard
- Jumper wires + harness
- Battery pack
- Status LEDs
- STRUCTURE & TRACKS
- Hull and motion
- 11
- unique structural parts
- 2 x hull side panels (rhomboidal)
- 1 x central cabin / electronics tub
- 4 x drive and idler wheels
- 2 x track shafts (barrod)
- Stepper bracket + nameplate
- 148 x track links
- 150 x plain rivets

_Images: media/slide02_img2.jpg_

## Slide 3: 02.
_intent: `contact`_

- INSPIRATION & PURPOSE
- An old shape for an educational lesson and potential platform for autonomous vehicle design
- THE
- SILHOUETTE
- a rhomboidal hull from 1916, a supply non-battle vehicle
- WHAT THIS BUILD IS
- A hands-on platform for understanding differential gears and embedded control
- The drivetrain sits open in the cabin so the differential is visible while it works. The rhomboidal hull gives a long ground-contact length and a high approach angle, useful as a stable, slow demonstrator that can additionally demonstrate difficult terrain navigation
- The Arduino runs open-loop step counting today. Adding encoders, an IMU, and feedback loops would turn it into a closed-loop platform, and the wiring leaves room for that step.
- Intended user:  engineering students learning about mechanical vehicle and track design and embedded control; autonomous vehicle engineers
- ETAD 130  ·  B. MIRONOV
- Inspiration & Purpose
- 3 / 13
- Fig. 2   The rhomboidal hull shape that offers superior terrain maneuver capabilities for crossing obstacles
- An autonomous stack-embedded tracked vehicle platform
- It can potentially include obstacle avoidance via ultrasonic or LiDAR, and vision-guided navigation and waypoint following, making way for creating a fully autonomous area patrol or research vehicle

_Images: media/slide03_img1.gif, media/slide03_img2.jpg_

## Slide 4: 03.
_intent: `how_it_works`_

- THE DRIVETRAIN
- How it steers: historical accuracy and single motor setupv
- ETAD 130  ·  B. MIRONOV
- Drivetrain
- 4 / 13
- NEMA 17
- stepper
- bevel pinion
- input
- crown gear
- reduction
- DIFFERENTIAL
- spider + side gears
- L + R outputs
- two independent track shafts
- Fig. 2   Power flow.  The crown gear drives the differential carrier; the side gears pass torque to two independent output shafts.
- THE PRINCIPLE
- How it works
- HISTORY
- How 1916 did it
- THIS BUILD
- How this build does it
- Differential
- Torque distribution
- TRY IT

_Images: media/slide04_img1.jpg, media/slide04_img2.jpg, media/slide04_img3.png, media/slide04_img4.png, media/slide04_img5.jpg, media/slide04_img6.jpg, media/slide04_img7.jpg, media/slide04_img8.png, media/slide04_img9.png_

## Slide 5: 04.
_intent: `content`_

- EXPLODED VIEW
- Every part of the core structural design:
- 1
- hullside1.ipt
- two side panels
- 2
- centralcabin.ipt
- electronics tub
- 3
- wheeldrive.ipt
- drive + idler wheels
- 4
- gearassembly.iam
- Differential-bevel gear
- 5
- barrod.ipt
- track shafts
- 6
- bracket.ipt
- stepper bracket
- ETAD 130  ·  B. MIRONOV
- Exploded View
- 5 / 13
- 1
- 1
- 2
- 3
- 4
- 4
- 5
- 5
- 6

_Images: media/slide05_img1.jpg_

## Slide 6: 05.
_intent: `content`_

- PARTS INVENTORY
- What is in the assembly.
- ETAD 130  ·  B. MIRONOV
- Parts Inventory
- 6 / 13

_Tables on slide: 1_

## Slide 7: 06.
_intent: `content`_

- TECHNICAL DRAWINGS
- Views, dimensions, and labels.
- Sheet 01   FRONT VIEW
- Sheet 02  SIDE VIEW
- Sheet 02      TOP VIEW
- Sheet 01     ISOMETRIC
- Source files:   BMironov_Tracked.dwg   ·   BMironov_TrackedFull.pdf
- ETAD 130  ·  B. MIRONOV
- Drawings
- 7 / 13
- Sheet 03 HULL  SIDE VIEW
- Sheet 02    HULL ISOMETRIC

_Images: media/slide07_img1.png, media/slide07_img2.png, media/slide07_img3.png, media/slide07_img4.png, media/slide07_img5.png, media/slide07_img6.png_

## Slide 8: 07.
_intent: `testimonial`_

- DIMENSION COMPARISON
- CAD model vs. printed part.
- CRITICAL DIMENENTIONS
- Track-link pin holes.
- Tightest tolerance in the build. Under-print: rivets do not seat. Over-print: links wobble. Most important for driving.
- Shafts and bores.
- PLA shrinks circular features: shafts smaller, bores larger. Useful here as a clearance fit.
- 1.0% acceptable    1.0–3.0% review    > 3.0% critical.
- ETAD 130  ·  B. MIRONOV
- Dimensions
- 8 / 13

_Tables on slide: 1_

## Slide 9: Part Simulation Highlights – main hull
_intent: `content`_


_Images: media/slide09_img1.jpg, media/slide09_img2.png, media/slide09_img3.jpg, media/slide09_img4.jpg_

## Slide 10: Part Simulation Highlights – main driving wheel
_intent: `content`_


_Images: media/slide10_img1.jpg, media/slide10_img2.jpg_

## Slide 11: 09.
_intent: `pricing`_

- WASTE & COST ANALYSIS
- Filament accounting.
- TOTAL FILAMENT
- ~990 g
- approximately one spool of PLA
- TOTAL COST
- ~$19.80
- at $20 per kilogram
- WASTE
- 0 %
- no supports, no purge, no failed prints
- MASS BY PART GROUP
- WHY ZERO WASTE
- Three choices allowed it:
- Print orientation.
- Every part was placed flat-side-down or on its widest face. No overhangs steeper than 45 degrees
- Single-color PLA per each part.
- One color, one nozzle. No purge towers and no filament-change waste.
- No failed prints.
- Each part came off the bed first try.
- ETAD 130  ·  B. MIRONOV
- Cost Analysis
- 12 / 13
- cost  =  (m_part + m_supports + m_purge) x (price_per_kg / 1000)
- Total filament mass: ~990 g PLA price: $20.00 / kg = $0.020 / g
- Total cost = 990 g × $0.020/g = $19.80

_Tables on slide: 1_

## Slide 12: 08.
_intent: `content`_

- PRINT & ASSEMBLY
- Time taken
- TOTAL PRINT TIME
- 7 h
- all main parts on the Bambu Lab
- TOTAL ASSEMBLY TIME
- 18 h
- bench work, by hand
- from first layer to a finished vehicle
- PRINT TIME
- ASSEMBLY TIME — BY PHASE
- ETAD 130  ·  B. MIRONOV
- Print & Assembly
- 11 / 13
- OVERALL TIME
- 25 h

_Tables on slide: 2_

## Slide 13: 11.
_intent: `content`_

- LIMITATIONS & FUTURE WORK
- What it cannot do, and what is next.
- LIMITATIONS
- Track tensioner - one side.
- The tracks were printed on two different machines (Dreamer + Ender). Dimensional drift between them left one loop slightly looser, so a printed tensioner was added on that side.
- Single-motor differential  - practical side
- Both tracks share one input. There is no active steering - the differential responds to load, not command.
- PLA fatigue at the link pin holes.
- 148 holes flexing every revolution. PLA is not fatigue-friendly; holes elongate over time.
- Welded rivet heads.
- Soldering-iron welds hold well at rest but can shear under repeated bending stress.
- FUTURE IMPROVEMENTS
- Dual-stepper drive.
- One motor per track.
- TPU for tracks and rivets.
- Better fatigue life, quieter operation, and rivets that bend instead of shear.
- Single-machine track print.
- Reprint all 148 links on one printer. Removes the dimensional drift that required the tensioner.
- Closed-loop feedback.
- Add an IMU and wheel encoders. Move from open-loop step counting to actual heading control.
- ETAD 130  ·  B. MIRONOV
- Limitations & Future
- 12 / 13

_Images: media/slide13_img1.jpg_

## Slide 14: Thank you.
_intent: `cta_or_closing`_

- Questions are welcome.
- REFERENCES
- Adafruit Industries (2025).  TB6612 1.2A DC/Stepper Motor Driver.  learn.adafruit.com
- Arduino (n.d.).  Stepper Library Reference.  arduino.cc/en/Reference/Stepper
- Wong, J. Y. (2008).  Theory of Ground Vehicles (4th ed.).  John Wiley & Sons.
- Autodesk (n.d.).  Inventor Help — Assemblies and Drawings.  help.autodesk.com
- Bambu Lab (n.d.).  Bambu Studio User Manual.  bambulab.com
- B. Mironov  ·  ETAD 130  ·  Spring 2026
- ETAD 130  ·  B. MIRONOV
- END
- 13 / 13