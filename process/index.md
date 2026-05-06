---
layout: page
title: "Print and assembly photo log"
permalink: /process/
eyebrow: "How it was built"
lede: "Slicer screenshots from Bambu Studio, bench shots during assembly, and the finished hull. The print plan, the welding plan, and the fit-up issues that came out of each step."
---

<section class="prose">
  <h2>Print plan</h2>
  <p>Twelve unique parts. Two of some, four of others. All on the Bambu Lab. The numbers below come straight from Bambu Studio's slicing report. Model time, plus a small overhead per plate for prepare and timelapse generation.</p>
</section>

<div class="cols cols--3">
  <figure class="figure">
    <img src="{{ '/assets/images/slice-cabin.jpg' | relative_url }}" alt="Bambu Studio slicing screenshot of the central cabin part placed flat on the build plate. The right panel reports 45.94 m of filament, 139.21 g, $3.48 cost, and 3 hours 24 minutes total time including prep.">
    <figcaption><strong>Central cabin.</strong> 139.21 g of filament. 3 h 7 m of print time. 3 h 24 m total. One per build.</figcaption>
  </figure>

  <figure class="figure">
    <img src="{{ '/assets/images/slice-hullside.png' | relative_url }}" alt="Bambu Studio slicing screenshot of one rhomboidal hullside panel placed flat on the build plate. The slicing panel reports 23.51 m of filament, 71.24 g, and 1 hour 27 minutes model print time, 1 hour 34 minutes total.">
    <figcaption><strong>Hullside.</strong> 71.24 g of filament. 1 h 27 m of print. 1 h 34 m total. Two per build, one per plate.</figcaption>
  </figure>

  <figure class="figure">
    <img src="{{ '/assets/images/slice-wheel.jpg' | relative_url }}" alt="Bambu Studio slicing screenshot of one drive wheel placed flat on the build plate. The slicing panel reports 1.67 m of filament, 5.07 g, $0.13 cost, and 9 minutes 20 seconds model print time, 16 minutes 32 seconds total.">
    <figcaption><strong>Drive wheel.</strong> 5.07 g. 9 m 20 s of print. 16 m 32 s total. Eight per build, batched four to a plate.</figcaption>
  </figure>
</div>

<section class="prose">
  <h2>Build photos</h2>
  <p>A few bench shots during the build. Soldering the controller. A track print pass on the Ender. The fit-up of the cabin electronics.</p>
</section>

<div class="cols cols--3">
  <figure class="figure">
    <img src="{{ '/media/controllersoldering.jpeg' | relative_url }}" alt="A small breadboard sits on a green cutting mat. A soldering iron tip touches a small Adafruit driver board mounted on the breadboard. A solder spool sits at upper left.">
    <figcaption><strong>Soldering the controller.</strong> Header pins on the driver board. Iron at 320 C, lead-free solder.</figcaption>
  </figure>

  <figure class="figure">
    <img src="{{ '/media/enderextraprintbed_tracks.jpeg' | relative_url }}" alt="Close-up of an Ender 3D printer bed with the words ENDER and a dragon logo printed on it. The fan and extruder block sit at the top, mid-print.">
    <figcaption><strong>Tracks on the Ender.</strong> Extra batch of links during a busy night. The Bambu carried most parts.</figcaption>
  </figure>

  <figure class="figure">
    <img src="{{ '/assets/images/electronics-bench.jpg' | relative_url }}" alt="Top-down photo of the cabin during electronics fit-up. A black USB power bank sits on the left. A black NEMA 17 stepper sits centered with a printed bevel pinion on its shaft and white bevel-gear spider gears mating against it. A breadboard with the TB6612 driver mounted on it sits below, and jumper wires run between the parts.">
    <figcaption><strong>Electronics fit-up.</strong> The bevel pinion is on the motor shaft. The spider gears are aligned against the side gears below.</figcaption>
  </figure>
</div>

<section class="prose">
  <h2>Assembly</h2>
  <p>Eighteen bench hours, broken across six phases. Track welding alone took eight of those hours. By far the dominant chunk. Everything else fits in two hour blocks. Print cleanup, hull assembly, drivetrain, electronics, fit-up.</p>
  <p>The welding rhythm is simple. Thread a PLA rivet through two link holes. Hold the rivet with one hand. Touch a 30 W soldering iron to the rivet head with the other. The PLA softens in about three seconds. Pressing the head with the iron tip mushrooms it over the link face. Done correctly, the rivet looks domed on both sides and the link rotates freely.</p>
</section>

<div class="cols cols--3">
  <figure class="figure">
    <img src="{{ '/assets/images/track-detail.jpg' | relative_url }}" alt="Close-up of a yellow drive sprocket meshing with the printed track. Track links alternate red, blue, and white. Black PLA rivets join each link to the next. The four square cutouts on the wheel rim engage the inside teeth of the track loop.">
    <figcaption><strong>Drive sprocket.</strong> The four 90 degree cutouts on the wheel rim drop into the link teeth. That mesh turns shaft rotation into track motion.</figcaption>
  </figure>

  <figure class="figure">
    <img src="{{ '/assets/images/vehicle-side-blue.jpg' | relative_url }}" alt="Side view of the finished vehicle on a polished concrete floor. Blue rhomboidal hull panel, four blue spoked drive wheels, complete track loop in alternating red, blue, and white links wrapping the full silhouette.">
    <figcaption><strong>Closed and tensioned.</strong> Track loop complete on one side. Front wheel, two carriers, drive sprocket at the rear.</figcaption>
  </figure>

  <figure class="figure">
    <video controls preload="metadata" poster="{{ '/assets/images/vehicle-top.png' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
      <source src="{{ '/media/movement.mp4' | relative_url }}" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption><strong>Movement clip.</strong> Original WMV converted to MP4 for the browser. <a href="{{ '/media/movement.wmv' | relative_url }}">Download the original WMV</a>.</figcaption>
  </figure>
</div>

<section class="prose">
  <h2>Print cleanup, what each part needed</h2>
  <p>Every printed bore got reamed by hand. The 0.30 in shaft holes (wheel bores, hullside shaft holes, bevel gear bores) came out 4 to 6 percent under their design diameter. A hand reamer at the design size cleared each one in a few seconds. Without the ream, the shaft would not seat or would bind the wheel against the panel.</p>
  <p>Every panel edge got a light deburr with a hobby knife. The Bambu's first layer outline left a small flange where the print started. The flange interfered with the cabin slot fit until it was scraped off.</p>
  <p>No part needed sanding for cosmetic reasons. PLA at 0.16 mm layer height looks fine on a non-decorative build like this.</p>

  <h2>Issues encountered</h2>

  <h3>Track loops printed at different sizes</h3>
  <p>The 148 track links printed in batches across multiple plates. Small drift between batches added up across the full loop length. One of the two assembled loops came out about 1.5 percent longer than the other. A printed tensioner, a flat tongue inside the loop, took up the slack on the looser side.</p>

  <h3>Bevel gears bound at first dry-fit</h3>
  <p>The crown gear's bore was 0.288 in printed, against the 0.300 in carrier shaft design. The crown would not seat on the carrier. I drilled it out to size with a hand drill at low RPM. The same fix worked on the pinion to motor shaft fit.</p>

  <h3>Hull to cabin slot was a friction fit</h3>
  <p>The 0.110 in hullside thickness printed at 0.118 in. The cabin slots designed for 0.110 in tabs were a little tight. I worked the panels in by hand. They could be opened up with a single pass of a flat file but they did not need it.</p>

  <h2>Drive demos</h2>
  <p>Two short clips of the vehicle in motion. Both files play in any modern browser.</p>
</section>

<div class="cols cols--2">
  <figure class="figure">
    <video controls preload="metadata" poster="{{ '/assets/images/vehicle-side-blue.jpg' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
      <source src="{{ '/media/straightmovement.mp4' | relative_url }}" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption><strong>Straight line drive.</strong> Both tracks at the same speed.</figcaption>
  </figure>

  <figure class="figure">
    <video controls preload="metadata" poster="{{ '/assets/images/diff-real.jpg' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
      <source src="{{ '/media/turningmovement.mp4' | relative_url }}" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption><strong>Turning.</strong> The differential gives one side less rotation when it loads up.</figcaption>
  </figure>
</div>
