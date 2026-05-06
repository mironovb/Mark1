---
layout: default
title: "A Differential Gear Learning Platform"
permalink: /
description: "Final project portfolio. A 1916 silhouette tracked vehicle, modeled in Inventor, printed in PLA, driven by an Arduino and a single stepper motor."
---

<section id="overview" class="hero">
  <div class="wrap hero__grid">
    <div>
      <div class="hero__eyebrow">{{ site.data.site.course }} · Final project · {{ site.data.site.semester }}</div>
      <h1 class="hero__title">A differential gear learning platform.</h1>
      <p class="hero__sub">A tracked vehicle with a rhomboidal hull. I modeled it in Autodesk Inventor. I printed it in PLA. I assembled it by hand. An Arduino drives it through one stepper motor and a printed bevel gear differential.</p>
      <div class="hero__meta">
        <div class="hero__meta-item">
          <span class="hero__meta-label">Author</span>
          <span class="hero__meta-value">{{ site.data.site.author }}</span>
        </div>
        <div class="hero__meta-item">
          <span class="hero__meta-label">Instructor</span>
          <span class="hero__meta-value">{{ site.data.site.instructor }}</span>
        </div>
        <div class="hero__meta-item">
          <span class="hero__meta-label">Institution</span>
          <span class="hero__meta-value">{{ site.data.site.institution }}</span>
        </div>
      </div>
    </div>
    <figure class="hero__photo">
      <img src="{{ '/assets/images/prototype-side.jpg' | relative_url }}" alt="The finished prototype on a polished concrete floor, side view. Blue rhomboidal hull, red and blue track links, four spoked drive wheels, a yellow drive sprocket, and a Bogdan nameplate on the side panel.">
    </figure>
  </div>
</section>

<section class="section">
  <div class="wrap">
    {% include stat-band.html stats=site.data.stats %}
  </div>
</section>

<section id="design" class="section">
  <div class="wrap">
    {% include section-header.html num="01" label="Design journey" title="What it is, and the choices that shaped it." sub="The build sets a 1916 hull silhouette on top of a modern drivetrain. One stepper motor drives two tracks through a real differential. Getting to that layout took a few rounds." %}

    <div class="prose">
      <p>The vehicle is a tracked platform. It has a central differential, a single NEMA 17 stepper, and an Arduino UNO. The Arduino runs open loop step control. Two side panels carry the chassis. A cabin between them holds the electronics. Two track shafts pass through the side panels and turn four drive wheels under 148 hand-welded track links.</p>
      <p>The shape is borrowed. It is the rhomboidal silhouette from a 1916 supply tracked vehicle. The mechanics are not borrowed. The 1916 vehicle steered with brake bands across an epicyclic gear. This build steers passively through a bevel gear differential. The electrical and control side is left open on purpose, ready for a closed loop upgrade.</p>
      <p>The choices below are the ones that changed between the first sketch and the version on the bench.</p>
    </div>

    <figure class="figure figure--wide figure--bleed">
      <img src="{{ '/media/labeledexplodedview.png' | relative_url }}" alt="Labeled CAD exploded view of the assembly. Numbered callouts list hullside1.ipt, centralcabin.ipt, wheeldrive.ipt, gearassembly.iam, barrod.ipt, and bracket.ipt.">
      <figcaption>Labeled exploded view of the core structural design. Six numbered callouts match the six file names on the right.</figcaption>
    </figure>

    <div class="decisions">
      {% for c in site.data.changes %}
      <div class="decision">
        <div class="decision__num">{{ forloop.index | prepend: '0' | slice: -2, 2 }}</div>
        <div class="decision__body">
          <h4>{{ c.heading }}</h4>
          <p>{{ c.body }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</section>

<section id="inspirations" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="02" label="Inspirations" title="An old shape, picked because it works." sub="The hull comes from a 1916 supply tracked vehicle. It was the smallest set of changes that gave the build the ground contact length it needed." %}

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/mark1-cutaway-1916.gif' | relative_url }}" alt="Black and white technical cutaway of a 1916 rhomboidal tracked vehicle. The tracks wrap around the full silhouette of the hull. Internal parts are labeled GearBox, Epicyclic Gear, Petrol Tank, Water Tank, Silencer, and Oil Tank.">
        <figcaption>1916 cutaway. The tracks follow the full hull silhouette. The gearbox and an epicyclic gear share a center compartment. The vehicle is about 26 ft 5 in long.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/mark1-museum.jpg' | relative_url }}" alt="Side view of a preserved 1916 Mark I tank in a museum. Riveted plate body, twin sponsons, and the long rhomboidal track loop wrapping the hull.">
        <figcaption>The hull silhouette in a museum. Long ground contact length and a high approach angle.</figcaption>
      </figure>
    </div>

    <div class="prose">
      <h3>The shape and why it works</h3>
      <p>A rhomboidal track loop puts a long stretch of track on the ground at any one time. That spreads the load. It gives the vehicle traction at low ground pressures. The high approach angle at the front lets the track climb up onto an obstacle instead of running into it. For a slow demonstrator that has to roll across uneven floors and small lips, the geometry pays for itself.</p>

      <h3>What the old design got right</h3>
      <p>One engine, one central reduction, one differential, and two outputs. The mechanical logic was visible from inside the hull. You could trace power from the engine to the tracks with your finger. The 1916 vehicle steered with brake bands across an epicyclic gear. That worked because the engine was always running. It is the wrong solution for a stepper.</p>

      <h3>What this build keeps and what it drops</h3>
      <p>This build keeps the silhouette and the central differential layout. It drops the brake band steering. There is no second controllable element, and adding one would mean adding a second motor. That sits on the future work list. The build adds an Arduino and a stepper driver where the petrol tank used to be. The gearbox compartment in the cutaway is now an open electronics tub. That choice is on purpose. The differential has to be visible while it works for the build to teach what it is supposed to teach.</p>
    </div>
  </div>
</section>

<section id="drivetrain" class="section">
  <div class="wrap">
    {% include section-header.html num="03" label="Drivetrain" title="One stepper, one differential, two tracks." sub="Power moves from a NEMA 17 stepper through a bevel pinion into the crown gear of the differential carrier. The carrier rotates. The two side gears feed the left and right track shafts on their own." %}

    <div class="flow">
      <div class="flow__step">
        <div class="flow__title">NEMA 17</div>
        <div class="flow__sub">stepper</div>
      </div>
      <div class="flow__step">
        <div class="flow__title">Bevel pinion</div>
        <div class="flow__sub">input</div>
      </div>
      <div class="flow__step flow__step--accent">
        <div class="flow__title">Differential</div>
        <div class="flow__sub">spider and side gears</div>
      </div>
      <div class="flow__step">
        <div class="flow__title">L and R outputs</div>
        <div class="flow__sub">two shafts</div>
      </div>
    </div>

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/diff-real.jpg' | relative_url }}" alt="Top-down photo of the printed differential mounted in the central cabin. White bevel gears mesh between two red drum collars on the green-tipped track shafts. The black NEMA 17 motor sits behind the gear pair.">
        <figcaption>The differential mounted in the cabin. The two red collars are the side-gear cups on the track shafts. The white spiders sit between them. The carrier holds the spiders against the side gears as the crown gear turns.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/diff-schematic.jpg' | relative_url }}" alt="Labeled schematic of an automotive style differential. A drive shaft enters from above through a drive pinion. The pinion meshes a ring gear that bolts to the carrier. Inside the carrier two differential pinions float between two side gears that drive the left and right axles.">
        <figcaption>Reference schematic. The build follows the same pattern with printed PLA gears and a 23 to 54 bevel pair preset.</figcaption>
      </figure>
    </div>

    <div class="prose">
      <h3>How tracked vehicles steer, in three sentences</h3>
      <p><strong>Skid steering</strong> drives the two tracks at different speeds and lets the slower track scrub on the ground. It needs a controllable element on each track. <strong>Brake band steering</strong> drives both tracks from one shaft and slows one side with a friction band. It needs a constantly driven shaft, which is why the 1916 vehicle's engine was always running. <strong>Hydrostatic steering</strong> uses two hydraulic motors and two pumps. It gives full control of each track but needs a hydraulic loop, which is too much at this scale.</p>

      <h3>How 1916 did it</h3>
      <p>One engine fed an epicyclic gear with two output drums. Brake bands wrapped each drum. Pulling one band slowed one track and the vehicle turned. It was mechanical, robust, and awful to control finely. The cutaway above shows the gear pair sitting where the petrol tank does not.</p>

      <h3>How this build does it</h3>
      <p>One stepper feeds the bevel pinion. The pinion turns the crown gear and rotates the differential carrier. Two side gears inside the carrier feed two output shafts. With both tracks unloaded the differential splits torque evenly and the vehicle drives straight. With one track loaded, say the inside track during a turn, the differential gives the loaded side less rotation and the unloaded side more. The vehicle responds to the ground. The controller does not yet know about it.</p>
    </div>

    <figure class="figure">
      <img src="{{ '/assets/images/diff-callout.png' | relative_url }}" alt="Colored illustration of a differential with three numbered callouts. 1 is the crown gear receiving torque from the pinion. 2 is the spider gears meshing inside the carrier. 3 is the axle shaft taking torque to the wheel.">
      <figcaption>1 the crown gear takes torque from the pinion. 2 the spider gears float inside the carrier. 3 the axle shaft carries torque to the track.</figcaption>
    </figure>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/nema17-stepper.jpg' | relative_url }}" alt="Pololu product photo of a NEMA 17 stepper motor, model SY42STH38-1684A. Square aluminum body, four mounting holes on the front face, a 5 mm shaft sticking out of the center.">
        <figcaption>NEMA 17 (SY42STH38). 200 steps per revolution at 1.8 degrees per step.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/bevel-cad-pair.jpg' | relative_url }}" alt="CAD render of the bevel gear pair. Small pinion at upper left meshes the large crown gear at right, both shown at 90 degrees to each other.">
        <figcaption>Bevel pair as rendered from the assembly. Ratio is 23 to 54.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/bevel-cad-closeup.png' | relative_url }}" alt="Close-up CAD render of the crown gear from the front face, with the pinion partly visible at the upper left. The center bore is dimensioned at 0.30 in.">
        <figcaption>Crown gear from the front. The 0.30 in bore takes the carrier shaft.</figcaption>
      </figure>
    </div>
  </div>
</section>

<section id="composition" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="04" label="Composition" title="Three systems, more than 180 components." sub="The build groups into a drivetrain (the gear pair), an electronics layer (Arduino and motor driver), and a structural layer (hull and tracks). Each is small enough to debug on its own." %}

    <div class="card-grid">
      <div class="card">
        <div class="card__eyebrow">Drivetrain</div>
        <h3 class="card__title">Differential gear</h3>
        <div class="card__metric">8</div>
        <div class="card__metric-sub">gear components</div>
        <ul class="card__list">
          <li><strong>Bevel pinion</strong><span>motor input</span></li>
          <li><strong>Crown gear</strong><span>speed reduction</span></li>
          <li><strong>Carrier housing</strong><span>rotates with the crown</span></li>
          <li><strong>2 side gears</strong><span>output to track shafts</span></li>
          <li><strong>2 spider gears</strong><span>the planet gears</span></li>
          <li><strong>Cross pin</strong><span>spider gear shaft</span></li>
        </ul>
      </div>

      <div class="card">
        <div class="card__eyebrow">Electronics</div>
        <h3 class="card__title">Control and power</h3>
        <div class="card__metric">7</div>
        <div class="card__metric-sub">electronic items</div>
        <ul class="card__list">
          <li><strong>Arduino UNO</strong><span>microcontroller</span></li>
          <li><strong>TB6612 driver</strong><span>stepper motor driver</span></li>
          <li><strong>NEMA 17</strong><span>stepper motor</span></li>
          <li><strong>Breadboard</strong><span>signal routing</span></li>
          <li><strong>Jumper wires and harness</strong><span>connections</span></li>
          <li><strong>Battery pack</strong><span>USB power bank</span></li>
          <li><strong>Status LEDs</strong><span>state indicators</span></li>
        </ul>
      </div>

      <div class="card">
        <div class="card__eyebrow">Structure and tracks</div>
        <h3 class="card__title">Hull and motion</h3>
        <div class="card__metric">11</div>
        <div class="card__metric-sub">unique structural parts</div>
        <ul class="card__list">
          <li><strong>2 hull side panels</strong><span>rhomboidal</span></li>
          <li><strong>1 central cabin</strong><span>electronics tub</span></li>
          <li><strong>4 drive and idler wheels</strong><span>four tread cutouts each</span></li>
          <li><strong>2 track shafts</strong><span>barrod, single piece</span></li>
          <li><strong>Stepper bracket and nameplate</strong><span>mount and ID</span></li>
          <li><strong>148 track links</strong><span>printed in two batches</span></li>
          <li><strong>150 plain rivets</strong><span>welded with an iron</span></li>
        </ul>
      </div>
    </div>

    <div class="composition-result">
      <strong>More than 180 individual components.</strong> Every one was designed in Inventor and assembled by hand.
    </div>

    <h3 style="margin-top: 3rem;">Every part by name</h3>
    <p class="prose">All ten unique parts in the bill of materials. Quantities, file names, and the drawing sheet that shows each part. The full description for each part lives on the <a href="{{ '/parts/' | relative_url }}">parts page</a>.</p>

    <div class="tbl-wrap">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Part name</th>
            <th>File</th>
            <th class="num">Qty</th>
            <th>Group</th>
            <th>Sheet</th>
          </tr>
        </thead>
        <tbody>
          {% for p in site.data.parts %}
          <tr>
            <td data-label="ID"><code>{{ p.id }}</code></td>
            <td data-label="Part"><strong>{{ p.name }}</strong></td>
            <td data-label="File"><code>{{ p.file }}</code></td>
            <td data-label="Qty" class="num">{{ p.qty }}</td>
            <td data-label="Group">{{ p.group | capitalize }}</td>
            <td data-label="Sheet">{% if p.drawing_sheet %}<a href="{{ '/drawings/sheet-' | append: p.drawing_sheet | append: '/' | relative_url }}">Sheet {{ p.drawing_sheet }}</a>{% else %}extra part{% endif %}</td>
          </tr>
          {% endfor %}
        </tbody>
      </table>
    </div>

    <figure class="figure" style="margin-top: 3rem;">
      <img src="{{ '/media/newtopview.jpeg' | relative_url }}" alt="Top-down photo of the assembled cabin. White bevel gear pair on top of the black NEMA 17 stepper. A red and green track shaft runs left to right. A black USB battery sits at upper left. A breadboard with a small driver board and a red controller PCB sit below. Blue and red track links wrap both sides.">
      <figcaption>Top view. The cabin is open on purpose. The bevel gear pair, the stepper, and the controller are all visible during a demo.</figcaption>
    </figure>
  </div>
</section>

<section id="visuals" class="section">
  <div class="wrap">
    {% include section-header.html num="05" label="Visual documentation" title="Listing of the drawings." %}

    <figure class="figure figure--wide">
      <img src="{{ '/assets/images/exploded-leaders.png' | relative_url }}" alt="CAD isometric of the full assembly with leader lines pulling each part group out to the side. Two side panels, four wheels, two track shafts, central cabin, motor bracket, and bevel gear pair. Each leader is numbered to a parts list.">
      <figcaption>Six callouts. 1 hullside1.ipt. 2 centralcabin.ipt. 3 wheeldrive.ipt. 4 gearassembly.iam. 5 barrod.ipt. 6 bracket.ipt. The full BOM lives on the parts page.</figcaption>
    </figure>

    <h3 style="margin-top: 3rem;">All seven drawing sheets</h3>
    <p class="prose">Here are the seven sheets at thumbnail size. Each tile opens the full sheet with its dimensions, scale, and part details. I drew the whole set from one Inventor assembly file.</p>

    <div class="drawings-grid">
      <a class="drawing-tile" href="{{ '/drawings/sheet-1/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-1.jpg' | relative_url }}" alt="Sheet 1 of 7. Isometric exploded view of Mark_Tracked_Vehicle with a six-row parts list.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 1 of 7</span>
          <span class="drawing-tile__title">Mark_Tracked_Vehicle</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-2/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-2.jpg' | relative_url }}" alt="Sheet 2 of 7. Hull and central cabin. Top, side, front, and isometric views with dimensions.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 2 of 7</span>
          <span class="drawing-tile__title">Hull (centralcabin)</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-3/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-3.jpg' | relative_url }}" alt="Sheet 3 of 7. Hullside. The rhomboidal side panel with overall length, height, and shaft hole dimensions.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 3 of 7</span>
          <span class="drawing-tile__title">Hullside</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-4/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-4.jpg' | relative_url }}" alt="Sheet 4 of 7. Rod (barrod). Side, end, top, and isometric views of the track shaft with collar.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 4 of 7</span>
          <span class="drawing-tile__title">Rod (barrod)</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-5/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-5.jpg' | relative_url }}" alt="Sheet 5 of 7. Wheel (wheeldrive). Front view with bore and tread dimensions, side view, and isometric.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 5 of 7</span>
          <span class="drawing-tile__title">Wheel (wheeldrive)</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-6/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-6.jpg' | relative_url }}" alt="Sheet 6 of 7. Enginemount. Front, top, side, and isometric views of the L-bracket with a 1.80 in motor bore.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 6 of 7</span>
          <span class="drawing-tile__title">Enginemount</span>
        </div>
      </a>
      <a class="drawing-tile" href="{{ '/drawings/sheet-7/' | relative_url }}">
        <img src="{{ '/assets/drawings/sheet-7.jpg' | relative_url }}" alt="Sheet 7 of 7. Bevelgears. Three views of the printed bevel gear pair at a 23 to 54 preset ratio.">
        <div class="drawing-tile__meta">
          <span class="drawing-tile__num">Sheet 7 of 7</span>
          <span class="drawing-tile__title">Bevelgears</span>
        </div>
      </a>
    </div>

    <p class="prose"><strong>Source files:</strong> <code>BMironov_Tracked.dwg</code> and <code>BMironov_TrackedFull.pdf</code>. I drew the sheets from <code>BMironov_TrackedMark.iam</code>, my top-level Inventor assembly.</p>

    <h3 style="margin-top: 3rem;">Drawing snapshots from the design slides</h3>
    <p class="prose">Smaller views pulled from the presentation. The same parts that appear on the formal sheets, shown in working CAD form during the design rounds.</p>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/cad-iso.png' | relative_url }}" alt="CAD isometric of the full assembled vehicle from a high front-quarter angle. Two side panels, four wheels, central cabin with bevel gear visible inside.">
        <figcaption>Assembled isometric, front-quarter view. The differential sits centered under the cabin opening.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/cad-iso-alt.png' | relative_url }}" alt="Second CAD isometric of the assembled vehicle from a different angle, showing the rear three-quarter view with the rear wheel pair and the back edge of the side panels.">
        <figcaption>Rear-quarter view. The rear shaft pad on the side panel is visible at lower right.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/exploded-cad.jpg' | relative_url }}" alt="CAD exploded view of the assembly: two rhomboidal side panels, central cabin, four wheels, two shafts, bevel gear pair, and motor bracket pulled apart along their assembly axes.">
        <figcaption>My working exploded view from the assembly file.</figcaption>
      </figure>
    </div>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/hullside-clean.png' | relative_url }}" alt="Clean profile drawing of the hullside panel as a single side view. 14.00 in length and 5.00 in height called out, both 0.30 in shaft holes marked, R1.00 fillet at the lower-front edge, 1.00 in pad at the rear shaft.">
        <figcaption>Hullside profile only. Same panel as the formal sheet, isolated for reference.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/hullside-iso.png' | relative_url }}" alt="Isometric CAD view of the hullside panel, showing the rhomboidal silhouette as a thin sheet with two small countersunk shaft holes.">
        <figcaption>Hullside isometric. The panel as it prints on the bed, flat side down.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/cabin-front.png' | relative_url }}" alt="Front orthographic view of the central cabin in CAD. Open top, U-channel walls, and the floor are visible. Two faint break lines at the top mark the side wall caps.">
        <figcaption>Cabin front view from the assembly file. The U-channel profile that the side panels seat into.</figcaption>
      </figure>
    </div>

    <h3 style="margin-top: 3rem;">Drawing descriptions</h3>
    <p class="prose">A short note for each of the six drawn parts. What it does, the main numbers on the sheet, and how it prints.</p>

    <div class="cols cols--2">
      <div class="prose">
        <h3>Hull side panels</h3>
        <p>Two mirrored rhomboidal panels carry the chassis. Each is 14.00 in long, 5.00 in tall, and 0.11 in thick. The shape comes from the 1916 silhouette. It has a long flat ground edge, a high front nose, and a slight dorsal angle that lifts the top edge above the cabin.</p>
        <p>Each panel prints flat on the build plate. A small 0.30 in shaft hole carries the front track shaft. The rear corner pad has a second hole for the rear shaft.</p>

        <h3>Central cabin</h3>
        <p>An open U-channel between the two side panels. It is 7.00 in long and 4.00 in tall. The 135 degree corner cuts at the front match the slope of the hull side panels, so the assembly sits flush. The cabin holds the Arduino, the TB6612 driver, the NEMA 17, and the battery pack. All of them are visible from above on purpose.</p>
      </div>

      <div class="prose">
        <h3>Drive and idler wheels</h3>
        <p>Eight wheels in total. Each is 5.00 in across and 1.00 in wide. Four square cutouts spaced 90 degrees apart around the rim mesh with the track link teeth. The bores are designed at 0.30 in to clearance fit the shafts. They printed about 6 percent undersized and were reamed by hand.</p>

        <h3>Bevel gear pair</h3>
        <p>Inventor's bevel gear preset at 23 to 54 teeth. The pinion sits on the motor shaft. The crown sits on the carrier of the differential. The bores were drilled out to match the printed shaft diameters after the first dry-fit failed.</p>
      </div>
    </div>

    <div class="cols cols--2">
      <div class="prose">
        <h3>Track shafts (barrod)</h3>
        <p>Single-piece print. 7.28 in long. A 0.30 in main shaft with a 1.00 in collar at the inboard end carries the side gear cup of the differential. The part prints standing on end on the bed. The seam runs along the shaft axis where it does not matter.</p>
      </div>
      <div class="prose">
        <h3>Stepper motor mount</h3>
        <p>An L-bracket. The vertical face has a 1.80 in bore that locates the NEMA 17 body. The horizontal base has two 0.30 in mounting holes. A 1.00 in inner radius sits where the bore meets the bracket face. Without it, the corner stress would crack on the second print.</p>
      </div>
    </div>

    <p class="prose"><a href="{{ '/drawings/' | relative_url }}">All seven drawing sheets</a> &nbsp;·&nbsp; <a href="{{ '/parts/' | relative_url }}">Full parts inventory</a> &nbsp;·&nbsp; <a href="{{ '/process/' | relative_url }}">Print and assembly photo log</a></p>
  </div>
</section>

<section id="motion" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="06" label="Drive demos" title="It moves." sub="Three short clips of the vehicle in motion. The MP4 files play in any modern browser. The original WMV is kept as a download for archive purposes." %}

    <div class="cols cols--2">
      <figure class="figure">
        <video controls preload="metadata" poster="{{ '/assets/images/vehicle-side-blue.jpg' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
          <source src="{{ '/media/straightmovement.mp4' | relative_url }}" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>Straight line drive. Both tracks move at the same speed and the vehicle rolls forward.</figcaption>
      </figure>

      <figure class="figure">
        <video controls preload="metadata" poster="{{ '/assets/images/diff-real.jpg' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
          <source src="{{ '/media/turningmovement.mp4' | relative_url }}" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>Turning. The differential gives the loaded side less rotation and the unloaded side more.</figcaption>
      </figure>
    </div>

    <figure class="figure">
      <video controls preload="metadata" poster="{{ '/assets/images/vehicle-top.png' | relative_url }}" style="width: 100%; border: 1px solid #DCE0D8; background: #F7F8F5;">
        <source src="{{ '/media/movement.mp4' | relative_url }}" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <figcaption>Original movement clip (movement.wmv, converted to MP4 for the browser). <a href="{{ '/media/movement.wmv' | relative_url }}">Download the original WMV</a>.</figcaption>
    </figure>
  </div>
</section>

<section id="dimensions" class="section">
  <div class="wrap">
    {% include section-header.html num="07" label="Dimensions" title="CAD model versus printed part." sub="I measured every printed feature with calipers and compared it back to the design value. Eleven features. One above 5 percent error. Three above 3 percent. The bores shrink. The thickness over-extrudes. The outer dimensions hold." %}

    <div class="cols cols--asym">
      <div>
        <div class="tbl-wrap">
          <table>
            <thead>
              <tr>
                <th>Feature</th>
                <th>Part</th>
                <th class="num">Design (in)</th>
                <th class="num">Printed (in)</th>
                <th class="num">Delta (in)</th>
                <th class="num">% error</th>
              </tr>
            </thead>
            <tbody>
              {% for r in site.data.dimensions.rows %}
              {% assign flag = '' %}
              {% if r.error_pct >= 3.0 %}{% assign flag = 'is-flag' %}{% endif %}
              <tr class="{{ flag }}">
                <td data-label="Feature">{{ r.feature }}</td>
                <td data-label="Part">{{ r.part }}</td>
                <td data-label="Design (in)" class="num">{{ r.design_in }}</td>
                <td data-label="Printed (in)" class="num">{{ r.printed_in }}</td>
                <td data-label="Delta (in)" class="num">{{ r.delta_in }}</td>
                <td data-label="% error" class="num">{{ r.error_pct }}%</td>
              </tr>
              {% endfor %}
            </tbody>
          </table>
        </div>

        <p class="note">Threshold bands. At or below 1.0 percent is acceptable. 1.0 to 3.0 percent gets a review. Above 3.0 percent is critical and is marked at the left margin. {{ site.data.dimensions.method.text }}</p>
      </div>

      <aside class="fits">
        <h3>Critical fits</h3>
        {% for f in site.data.dimensions.critical_fits %}
        <div class="fits__item">
          <div class="fits__heading">{{ f.heading }}</div>
          <p class="fits__body">{{ f.body }}</p>
        </div>
        {% endfor %}
      </aside>
    </div>

    <p class="prose">PLA shrinks round features more than rectangular ones. The bores all came out small. The outer length and height all came out close. The thickness ran the other way, with extra material at the wall, and is the only feature above 5 percent error. None of the deviations forced a redesign. Three of them, the wheel bore, the gear bore, and the hullside shaft hole, forced a hand ream pass after print.</p>
  </div>
</section>

<section id="process" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="08" label="Print and assembly" title="Seven hours on the printer, eighteen at the bench." sub="The print is the easy part. The bench work is dominated by track welding. There are 148 links and 150 PLA rivets, and every joint is melted with a soldering iron." %}

    {% assign tl = site.data.timeline %}

    <div class="stat-band">
      <div class="stat-band__item">
        <div class="stat-band__label">Total print time</div>
        <div class="stat-band__value">{{ tl.totals.print_h }} h</div>
        <div class="stat-band__sub">all main parts on the {{ tl.print_time.machine }}</div>
      </div>
      <div class="stat-band__item">
        <div class="stat-band__label">Total assembly time</div>
        <div class="stat-band__value">{{ tl.totals.assembly_h }} h</div>
        <div class="stat-band__sub">bench work, by hand</div>
      </div>
      <div class="stat-band__item stat-band__item--emph">
        <div class="stat-band__label">Overall</div>
        <div class="stat-band__value">{{ tl.totals.overall_h }} h</div>
        <div class="stat-band__sub">first layer to a finished vehicle</div>
      </div>
    </div>

    <div class="cols cols--2">
      <div>
        <h3>Print time on the Bambu Lab</h3>
        <div class="tbl-wrap">
          <table>
            <thead>
              <tr><th>Part</th><th class="num">Qty</th><th class="num">Hours</th></tr>
            </thead>
            <tbody>
              {% for r in tl.print_time.rows %}
              <tr>
                <td data-label="Part">{{ r.item }}</td>
                <td data-label="Qty" class="num">{{ r.qty }}</td>
                <td data-label="Hours" class="num">{{ r.hours }}</td>
              </tr>
              {% endfor %}
            </tbody>
            <tfoot>
              <tr>
                <td>Total</td>
                <td class="num">{{ tl.print_time.total_qty }}</td>
                <td class="num">{{ tl.print_time.total_hours }}</td>
              </tr>
            </tfoot>
          </table>
        </div>
      </div>

      <div>
        <h3>Assembly time, by phase</h3>
        <div class="tbl-wrap">
          <table>
            <thead>
              <tr><th>Phase</th><th>Work</th><th class="num">Hours</th></tr>
            </thead>
            <tbody>
              {% for r in tl.assembly_time.rows %}
              <tr {% if r.phase == "Track welding" %}class="is-flag"{% endif %}>
                <td data-label="Phase">{{ r.phase }}</td>
                <td data-label="Work">{{ r.work }}</td>
                <td data-label="Hours" class="num">{{ r.hours }}</td>
              </tr>
              {% endfor %}
            </tbody>
            <tfoot>
              <tr>
                <td>Total</td>
                <td>bench hours</td>
                <td class="num">{{ tl.assembly_time.total_hours }}</td>
              </tr>
            </tfoot>
          </table>
        </div>
      </div>
    </div>

    <p class="prose">Track welding ate the bench. 148 links plus 150 rivets is 298 small joints. Each rivet sits in two link holes. You push it through, hold it with one hand, and tap the head with the soldering iron until the PLA mushrooms. It takes about a minute per rivet once you have the rhythm. The first dozen take three.</p>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/slice-cabin.jpg' | relative_url }}" alt="Bambu Studio screenshot showing the central cabin part placed flat on the build plate. The slicing result panel reads 45.94 m of filament, 139.21 g, 3 hours 7 minutes model time, and 3 hours 24 minutes total.">
        <figcaption>Central cabin slice. 139.21 g and 3 h 7 m of model time on the Bambu.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/slice-hullside.png' | relative_url }}" alt="Bambu Studio screenshot of a hullside panel placed flat on the build plate. The slicing panel reports 23.51 m, 71.24 g, and 1 hour 27 minutes model time.">
        <figcaption>Hullside slice. 71.24 g and 1 h 27 m. Two of them per build.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/slice-wheel.jpg' | relative_url }}" alt="Bambu Studio screenshot of a single drive wheel placed flat on the build plate. The slicing panel reports 1.67 m, 5.07 g, and 9 minutes 20 seconds of model time.">
        <figcaption>One wheel. 5.07 g and 9 m 20 s. Eight of them per build, batched.</figcaption>
      </figure>
    </div>

    <h3 style="margin-top: 3rem;">Build photos</h3>
    <p class="prose">Bench shots from the build, including the controller soldering work and the printbed during a track print pass on the Ender. The Bambu carried most parts. The Ender ran a small batch of tracks during one of the busy nights.</p>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/media/controllersoldering.jpeg' | relative_url }}" alt="A small breadboard sits on a green cutting mat. A soldering iron tip touches a small Adafruit driver board mounted on the breadboard. Solder spool sits at upper left.">
        <figcaption>Soldering header pins onto the controller board on a green cutting mat. The Adafruit driver gets seated on the breadboard.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/media/enderextraprintbed_tracks.jpeg' | relative_url }}" alt="Close-up photo of an Ender 3D printer bed with the words ENDER and a dragon logo printed on it. The fan and extruder block sit at the top, mid-print.">
        <figcaption>Extra batch of tracks running on the Ender printbed. The Bambu carried most parts; the Ender helped on long nights.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/electronics-bench.jpg' | relative_url }}" alt="Top-down photo of the assembled cabin during electronics fit-up. A black power bank sits on the left. A NEMA 17 stepper sits centered with a bevel pinion on its shaft. White spider gears, a breadboard with a TB6612 driver below, and jumper wires run between.">
        <figcaption>Cabin during electronics fit-up. The bevel pinion is on the motor shaft. The differential carrier sits below.</figcaption>
      </figure>
    </div>

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/track-detail.jpg' | relative_url }}" alt="Close-up of a yellow drive wheel meshing with the printed track. The track links are red and blue PLA, joined by black rivets. The wheel teeth slot into the track link recesses.">
        <figcaption>Drive wheel meshing the track. The square cutouts on the wheel rim engage the link teeth.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/vehicle-side-blue.jpg' | relative_url }}" alt="Side view of the finished vehicle on a polished floor. Blue rhomboidal hull panel, four spoked wheels, complete track loop in alternating red, blue, and white links.">
        <figcaption>Finished hull on the floor. Track loop closed and tensioned.</figcaption>
      </figure>
    </div>
  </div>
</section>

<section id="cost" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="09" label="Filament and cost" title="One spool of PLA. Twenty dollars. No waste." sub="The whole build prints from about one kilogram of PLA. No supports, no purge towers, no failed prints. Mass and cost broken down by part group below." %}

    {% assign f = site.data.filament %}
    <div class="stat-band">
      <div class="stat-band__item">
        <div class="stat-band__label">Total filament</div>
        <div class="stat-band__value">~{{ f.total_mass_g }} g</div>
        <div class="stat-band__sub">about one spool of PLA</div>
      </div>
      <div class="stat-band__item">
        <div class="stat-band__label">Total cost</div>
        <div class="stat-band__value">~${{ f.total_cost_usd }}</div>
        <div class="stat-band__sub">at $20.00 per kilogram</div>
      </div>
      <div class="stat-band__item stat-band__item--emph">
        <div class="stat-band__label">Waste</div>
        <div class="stat-band__value">{{ f.waste_pct }} %</div>
        <div class="stat-band__sub">no supports, no purge, no failed prints</div>
      </div>
    </div>

    <div class="cols cols--asym">
      <div>
        <h3>Mass by part group</h3>
        <div class="tbl-wrap">
          <table>
            <thead>
              <tr>
                <th>Part group</th>
                <th class="num">Qty</th>
                <th class="num">Mass (g)</th>
                <th class="num">% of total</th>
              </tr>
            </thead>
            <tbody>
              {% for g in f.groups %}
              <tr>
                <td data-label="Part group">{{ g.name }}</td>
                <td data-label="Qty" class="num">{{ g.qty }}</td>
                <td data-label="Mass (g)" class="num">~{{ g.mass_g }}</td>
                <td data-label="% of total" class="num">{{ g.pct }} %</td>
              </tr>
              {% endfor %}
            </tbody>
            <tfoot>
              <tr>
                <td>Total</td>
                <td class="num"></td>
                <td class="num">~{{ f.total_mass_g }}</td>
                <td class="num">100 %</td>
              </tr>
            </tfoot>
          </table>
        </div>

        <h3>The math</h3>
        <div class="calc">cost = (m_part + m_supports + m_purge) * (price_per_kg / 1000)
<br>
<br><strong>Total mass:</strong>  990 g
<br><strong>PLA price:</strong>   $20.00 / kg  =  $0.020 / g
<br><strong>Total cost:</strong>  990 g * $0.020 / g  =  <strong>$19.80</strong>
<br>
<br><strong>Waste:</strong>       0 g supports + 0 g purge + 0 g failed  =  <strong>0 g  =  0 %</strong></div>
      </div>

      <aside class="fits">
        <h3>Why zero waste</h3>
        {% for r in f.zero_waste_reasons %}
        <div class="fits__item">
          <div class="fits__heading">{{ r.heading }}</div>
          <p class="fits__body">{{ r.body }}</p>
        </div>
        {% endfor %}
      </aside>
    </div>
  </div>
</section>

<section id="reflection" class="section">
  <div class="wrap">
    {% include section-header.html num="10" label="Reflection and future" title="What did not work. What I would change. What I learned." sub="The vehicle drives. It also drifts toward one side. It runs through tensioner adjustments faster than I expected. It would not survive an hour on a hard floor. Everything below is honest." %}

    <div class="reflect">
      <div class="reflect__group">
        <h3>What did not work the first time</h3>
        <p>The first hull layout drove the rear wheel pair. The differential was at the back of the cabin. The side gears had to push torque through the long shafts under load. Moving the drive forward shortened the load path. The bracket now sits where the cabin is widest.</p>
        <p>The first drivetrain used a fixed bevel reduction. One input, one shaft, two slip-fit wheels. It rolled in a straight line. It then wound up against itself the moment a track caught a lip. Replacing the fixed pair with a real differential gave the two outputs independent speed.</p>
        <p>Three printed bores came out small. The wheel bores were 6.00 percent under (0.282 in versus a 0.300 in design). The hullside shaft holes were 4.67 percent under. The bevel gear bores were 4.00 percent under. All three got reamed by hand during the print cleanup phase. None of them came out of the printer ready to use. That should have been planned in from the start.</p>
        <p>One side of the track came out looser than the other. Small drift between the two link batches added up across the loop length. A printed tensioner, a flat tongue against the inside of the loop, took up the slack. The fix works. The tensioner is a part the design did not plan for. Tighter batch to batch control would prevent the need for it.</p>
      </div>

      <div class="reflect__group">
        <h3>What I would do differently next build</h3>
        {% for f in site.data.future %}
        <h4>{{ f.heading }}</h4>
        <p>{{ f.body }}</p>
        {% endfor %}
      </div>

      <div class="reflect__group">
        <h3>What I learned</h3>
        <p>The clear lesson is on tolerances. PLA shrinks round features and adds material at flat walls. The design has to plan for both. The clearance fit bores should have been designed at 0.318 in if the printed result needed to be 0.300 in. Knowing the direction PLA moves is half the work. The other half is committing to that direction in the model instead of reaming after print.</p>
        <p>The other lesson is on motors and steering. A single drive source plus a passive differential teaches the differential. It does not make a useful vehicle. Two motors and a closed loop heading reference is where this build wants to go next. The hardware path is clear. The work is the controller.</p>
        <p>The third, smaller lesson is on assembly time. The print plan accounted for hours on the printer. The welding plan did not account for the eight bench hours of soldering iron work. The next plan budgets the assembly time honestly, because that is where the schedule actually sits.</p>
      </div>
    </div>

    <figure class="figure figure--inset" style="margin-top: 3rem;">
      <img src="{{ '/assets/images/tensioner.jpg' | relative_url }}" alt="Close-up of one corner of the hull showing a printed tensioner. A flat blue tongue projects outward and presses against the inside of the track loop to take up slack.">
      <figcaption>The blue tongue is the printed tensioner. It took up the slack on the looser of the two track loops.</figcaption>
    </figure>
  </div>
</section>

<section id="references" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="11" label="References" title="Sources used in the build." sub="Six sources, grouped by what they helped me do. Two hardware references for the motor driver and the stepper code. One textbook for tracked vehicle steering theory. Two software manuals for Inventor and Bambu Studio. One historical record for the hull silhouette." %}

    <div class="prose">
      <p>How to read each entry. The first line is the citation in author, year, title, and source format. The second line, marked <strong>Used for</strong>, says what part of the build I took from that source and where it shows up. If the source is online, the citation ends with the domain so you can find the page. Print sources end with the publisher.</p>
    </div>

    <ol class="refs">
      {% for r in site.data.references %}
      <li>
        {{ r.citation }}
        <span class="used-for"><strong>Used for:</strong> {{ r.used_for }}</span>
      </li>
      {% endfor %}
    </ol>
  </div>
</section>

<section id="tryit" class="section">
  <div class="wrap">
    {% include section-header.html num="12" label="Try it" title="Scan for the differential GIF." sub="A QR code that opens an animated GIF showing the differential at work. Point a phone camera at the code. The GIF shows the spider gears walking between the two side gears as the carrier rotates." %}

    <figure class="figure figure--inset" style="margin: 0 auto;">
      <img src="{{ '/media/tryitgifqr.png' | relative_url }}" alt="A QR code labeled TRY IT in green letters at the top. Standard square QR pattern below.">
      <figcaption>QR code that links to a GIF of the differential function. The label reads TRY IT in green at the top.</figcaption>
    </figure>
  </div>
</section>
