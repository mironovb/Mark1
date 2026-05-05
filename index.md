---
layout: default
title: "A Differential-Gear Learning Platform"
permalink: /
description: "Final project portfolio. A 1916-silhouette tracked vehicle, modeled in Inventor, printed in PLA, driven by an Arduino and a single stepper motor."
---

<section id="overview" class="hero">
  <div class="wrap hero__grid">
    <div>
      <div class="hero__eyebrow">{{ site.data.site.course }} · Final project · {{ site.data.site.semester }}</div>
      <h1 class="hero__title">A differential-gear learning platform.</h1>
      <p class="hero__sub">A rhomboidal-hulled tracked vehicle. Modeled in Autodesk Inventor, 3D-printed in PLA, assembled by hand, driven by an Arduino through one stepper motor and a printed bevel-gear differential.</p>
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
      <img src="{{ '/assets/images/prototype-side.jpg' | relative_url }}" alt="The finished prototype standing on a polished concrete floor, side view. Blue rhomboidal hull, red and blue track links, four spoked drive wheels, a yellow drive sprocket, and a Bogdan nameplate on the side panel.">
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
    {% include section-header.html num="01" label="Design journey" title="What it is, and the decisions that got it there." sub="The build sets a 1916 hull silhouette on top of a modern drivetrain so a single stepper motor can drive two tracks through a true differential. The path to that arrangement was not the first sketch." %}

    <div class="cols cols--asym">
      <div class="prose">
        <p>The vehicle is a tracked platform with a central differential, a single NEMA 17 stepper, and an Arduino UNO running open-loop step control. Two side panels carry the chassis. A cabin between them carries the electronics. Two track shafts ride through the side panels and turn four drive wheels under 148 hand-welded track links.</p>
        <p>The form is borrowed: a rhomboidal silhouette from a 1916 supply tracked vehicle. The mechanics are not. The 1916 vehicle steered with brake bands across an epicyclic gear; this build steers passively through a bevel-gear differential and intentionally leaves the electrical and control side open for a closed-loop upgrade.</p>
        <p>The decisions below are the ones that changed the build between the first sketch and the version on the bench.</p>
      </div>

      <figure class="figure">
        <img src="{{ '/assets/images/exploded-cad.jpg' | relative_url }}" alt="CAD exploded view of the assembly: two rhomboidal side panels, central cabin, four wheels, two shafts, bevel-gear pair, and motor bracket pulled apart along their assembly axes.">
        <figcaption>Exploded view of the core structural design — generated from BMironov_TrackedMark.iam.</figcaption>
      </figure>
    </div>

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
    {% include section-header.html num="02" label="Inspirations" title="An old shape, picked because it works." sub="The hull comes from a 1916 supply tracked vehicle. The shape was not nostalgia — it was the smallest set of changes that gave the build the ground-contact length it needed." %}

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/mark1-cutaway-1916.gif' | relative_url }}" alt="Black-and-white technical cutaway of a 1916 rhomboidal tracked vehicle. Tracks wrap around the full silhouette of the hull. Internal components labelled GearBox, Epicyclic Gear, Petrol Tank, Water Tank, Silencer, Oil Tank.">
        <figcaption>1916 cutaway. The tracks follow the full hull silhouette; the gearbox and an epicyclic gear share a center compartment. Length 26 ft 5 in approx.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/mark1-museum.jpg' | relative_url }}" alt="Side view of a preserved 1916 Mark I tank in a museum. Riveted plate construction, twin sponsons, and the long rhomboidal track loop wrapping the hull.">
        <figcaption>The actual hull silhouette in a museum. Long ground-contact length, high approach angle.</figcaption>
      </figure>
    </div>

    <div class="prose">
      <h3>The shape and why it works</h3>
      <p>A rhomboidal track loop puts a long stretch of track on the ground at any one time. That spreads the load and gives the vehicle traction at low ground pressures. The high approach angle at the front lets the track climb up onto an obstacle instead of running into it. For a slow demonstrator that has to roll across uneven floors and small lips, the geometry pays for itself.</p>

      <h3>What the old design got right</h3>
      <p>One engine, one central reduction, one differential, two outputs. The mechanical logic was visible from the inside of the hull — you could trace power from the engine to the tracks with your finger. The 1916 vehicle steered with brake bands across an epicyclic gear; that worked because the engine was always running. It is the wrong solution for a stepper.</p>

      <h3>What this build keeps and what it drops</h3>
      <p>This build keeps the silhouette and the central-differential layout. It drops the brake-band steering — there is no second controllable element, and adding one would mean adding a second motor, which is on the future-work list. It adds an Arduino and a stepper driver where the petrol tank used to be. The gearbox compartment in the cutaway is now an open electronics tub, on purpose: the differential has to be visible while it works for the build to teach what it is supposed to teach.</p>
    </div>
  </div>
</section>

<section id="drivetrain" class="section">
  <div class="wrap">
    {% include section-header.html num="03" label="Drivetrain" title="One stepper, one differential, two tracks." sub="Power flows from a NEMA 17 stepper through a bevel pinion into the crown gear of the differential carrier. The carrier rotates; the two side gears feed the left and right track shafts independently." %}

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
        <div class="flow__sub">spider + side gears</div>
      </div>
      <div class="flow__step">
        <div class="flow__title">L + R outputs</div>
        <div class="flow__sub">two shafts</div>
      </div>
    </div>

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/diff-real.jpg' | relative_url }}" alt="Top-down photo of the printed differential mounted in the central cabin. White bevel gears mesh between two red drum-shaped collars on the green-tipped track shafts. The black NEMA 17 motor sits behind the gear pair.">
        <figcaption>The differential mounted in the cabin. The two red collars are the side-gear cups on the track shafts; the white spiders sit between them. The carrier is what holds the spiders against the side gears as the crown gear turns.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/diff-schematic.jpg' | relative_url }}" alt="Labelled schematic of an automotive-style differential. Drive shaft enters from above through a drive pinion. The pinion meshes a ring gear which is bolted to the carrier. Inside the carrier two differential pinions float between two side gears that drive the left and right axles.">
        <figcaption>Reference schematic. The build follows the same pattern with printed PLA gears and a 23 : 54 bevel-pair preset.</figcaption>
      </figure>
    </div>

    <div class="prose">
      <h3>How tracked vehicles steer, in three sentences</h3>
      <p><strong>Skid steering</strong> drives the two tracks at different speeds and lets the slower track scrub on the ground; needs a controllable element on each track. <strong>Brake-band steering</strong> drives both tracks from one shaft and slows one side with a friction band; needs a constantly-driven shaft, which is why the 1916 vehicle's engine was always running. <strong>Hydrostatic steering</strong> uses two hydraulic motors and two pumps; gives full control of each track but needs a hydraulic loop, which is overkill at this scale.</p>

      <h3>How 1916 did it</h3>
      <p>One engine fed an epicyclic gear with two output drums. Brake bands wrapped each drum; pulling one band slowed one track and the vehicle turned. Mechanical, robust, awful to control finely. The cutaway above shows the gear pair sitting where the petrol tank doesn't.</p>

      <h3>How this build does it</h3>
      <p>One stepper feeds the bevel pinion. The pinion turns the crown gear and rotates the differential carrier. Two side gears inside the carrier feed two output shafts. With both tracks unloaded the differential splits torque evenly and the vehicle drives straight. With one track loaded — say the inside track during a turn — the differential gives the loaded side less rotation and the unloaded side more. The vehicle responds to the ground; the controller does not yet know about it.</p>
    </div>

    <figure class="figure">
      <img src="{{ '/assets/images/diff-callout.png' | relative_url }}" alt="Coloured illustration of a differential with three numbered callouts: 1 the crown gear receiving torque from the pinion, 2 the spider gears meshing inside the carrier, 3 the axle shaft taking torque to the wheel.">
      <figcaption>1 the crown gear takes torque from the pinion. 2 the spider gears float inside the carrier. 3 the axle shaft carries torque to the track.</figcaption>
    </figure>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/nema17-stepper.jpg' | relative_url }}" alt="Pololu product photo of a NEMA 17 stepper motor, model SY42STH38-1684A. Square aluminium body, four mounting holes on the front face, a 5 mm shaft protruding from the centre.">
        <figcaption>NEMA 17 (SY42STH38). 200 steps per revolution at 1.8°.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/bevel-cad-pair.jpg' | relative_url }}" alt="CAD render of the bevel gear pair: small pinion at upper left meshing the large crown gear at right, both shown at 90° to each other.">
        <figcaption>Bevel pair as rendered from the assembly. 23 : 54 ratio.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/bevel-cad-closeup.png' | relative_url }}" alt="Close-up CAD render of the crown gear from the front face, with the pinion partially visible at the upper left. The Ø.30 in centre bore is dimensioned on the crown.">
        <figcaption>Crown gear from the front. The Ø0.30 in bore takes the carrier shaft.</figcaption>
      </figure>
    </div>
  </div>
</section>

<section id="composition" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="04" label="Composition" title="Three systems, 180+ components." sub="The build groups into a drivetrain (the gear pair), an electronics layer (Arduino and motor driver), and a structural layer (hull and tracks). Each is small enough to debug on its own." %}

    <div class="card-grid">
      <div class="card">
        <div class="card__eyebrow">Drivetrain</div>
        <h3 class="card__title">Differential gear</h3>
        <div class="card__metric">8</div>
        <div class="card__metric-sub">gear components</div>
        <ul class="card__list">
          <li><strong>Bevel pinion</strong><span>motor input</span></li>
          <li><strong>Crown gear</strong><span>speed reduction</span></li>
          <li><strong>Carrier housing</strong><span>rotates with crown</span></li>
          <li><strong>2 × side gears</strong><span>output to track shafts</span></li>
          <li><strong>2 × spider gears</strong><span>the planet gears</span></li>
          <li><strong>Cross pin</strong><span>spider-gear shaft</span></li>
        </ul>
      </div>

      <div class="card">
        <div class="card__eyebrow">Electronics</div>
        <h3 class="card__title">Control and power</h3>
        <div class="card__metric">7</div>
        <div class="card__metric-sub">electronic items</div>
        <ul class="card__list">
          <li><strong>Arduino UNO</strong><span>microcontroller</span></li>
          <li><strong>TB6612 driver</strong><span>stepper-motor driver</span></li>
          <li><strong>NEMA 17</strong><span>stepper motor</span></li>
          <li><strong>Breadboard</strong><span>signal routing</span></li>
          <li><strong>Jumper wires + harness</strong><span>connections</span></li>
          <li><strong>Battery pack</strong><span>USB power bank</span></li>
          <li><strong>Status LEDs</strong><span>state indicators</span></li>
        </ul>
      </div>

      <div class="card">
        <div class="card__eyebrow">Structure & tracks</div>
        <h3 class="card__title">Hull and motion</h3>
        <div class="card__metric">11</div>
        <div class="card__metric-sub">unique structural parts</div>
        <ul class="card__list">
          <li><strong>2 × hull side panels</strong><span>rhomboidal</span></li>
          <li><strong>1 × central cabin</strong><span>electronics tub</span></li>
          <li><strong>4 × drive and idler wheels</strong><span>tread cutouts ×4</span></li>
          <li><strong>2 × track shafts</strong><span>barrod, single-piece</span></li>
          <li><strong>Stepper bracket + nameplate</strong><span>mount + ID</span></li>
          <li><strong>148 × track links</strong><span>printed in two batches</span></li>
          <li><strong>150 × plain rivets</strong><span>welded with iron</span></li>
        </ul>
      </div>
    </div>

    <div class="composition-result">
      <strong>180+ individual components</strong> — every one designed in Inventor and assembled by hand.
    </div>

    <figure class="figure" style="margin-top: 3rem;">
      <img src="{{ '/assets/images/vehicle-top.png' | relative_url }}" alt="Top-down photo of the assembled vehicle. The two side panels frame a yellow electronics tub. Inside the tub: stepper motor, breadboard, jumper wires. Track loops on either side.">
      <figcaption>Top view. The cabin is open on purpose — the differential and the electronics are visible at any time during a demo.</figcaption>
    </figure>
  </div>
</section>

<section id="visuals" class="section">
  <div class="wrap">
    {% include section-header.html num="05" label="Visual documentation" title="Exploded view, every part on a sheet, every wheel on the bench." sub="The exploded image keys to the parts list. The drawings page carries one full sheet per part. The parts page carries every part with its description, file, and quantity." %}

    <figure class="figure figure--wide">
      <img src="{{ '/assets/images/exploded-leaders.png' | relative_url }}" alt="CAD isometric of the full assembly with leader lines pulling each part group out to the side. Two side panels, four wheels, two track shafts, central cabin, motor bracket, and bevel-gear pair. Each leader is numbered to a parts list.">
      <figcaption>Six callouts: 1 hullside1.ipt, 2 centralcabin.ipt, 3 wheeldrive.ipt, 4 gearassembly.iam, 5 barrod.ipt, 6 bracket.ipt. The full BOM lives on the parts page.</figcaption>
    </figure>

    <div class="cols cols--2">
      <div class="prose">
        <h3>Hull side panels</h3>
        <p>Two mirrored rhomboidal panels carry the chassis. 14.00 in long, 5.00 in tall, 0.11 in thick. The shape comes from the 1916 silhouette — a long flat ground edge, a high front nose, and a slight dorsal angle that lifts the top edge above the cabin.</p>
        <p>Printed flat on the build plate. The single small Ø0.30 in shaft hole carries the front track shaft; the rear corner pad has a second hole for the rear shaft.</p>

        <h3>Central cabin</h3>
        <p>Open U-channel between the two side panels. 7.00 in long, 4.00 in tall. The 135° corner cuts at the front match the slope of the hull-side panels so the assembly sits flush. The cabin holds the Arduino, the TB6612 driver, the NEMA 17, and the battery pack — all visible from above on purpose.</p>
      </div>

      <div class="prose">
        <h3>Drive and idler wheels</h3>
        <p>Eight wheels in total. Ø5.00 in diameter, 1.00 in wide. Four square cutouts spaced 90° apart around the rim mesh with the track-link teeth. The bores are designed Ø0.30 in to clearance-fit the shafts; in practice they printed about 6 % undersized and were reamed by hand.</p>

        <h3>Bevel-gear pair</h3>
        <p>Inventor's bevel-gear preset at 23 : 54 teeth. The pinion sits on the motor shaft; the crown sits on the carrier of the differential. The bores were drilled out to match the printed shaft diameters after the first dry-fit failed.</p>
      </div>
    </div>

    <div class="cols cols--2">
      <div class="prose">
        <h3>Track shafts (barrod)</h3>
        <p>Single-piece print. 7.28 in long. Ø0.30 in main shaft with a 1.00 in collar at the inboard end that carries the side-gear cup of the differential. Printed standing on end on the bed; the seam runs along the shaft axis where it doesn't matter.</p>
      </div>
      <div class="prose">
        <h3>Stepper-motor mount</h3>
        <p>L-bracket. The vertical face has a Ø1.80 in bore that locates the NEMA 17 body; the horizontal base has two Ø0.30 in mounting holes. R1.00 inner radius where the bore meets the bracket face — without it, the corner stress concentration would crack on the second print.</p>
      </div>
    </div>

    <div class="cols cols--2">
      <figure class="figure">
        <img src="{{ '/assets/images/cad-iso.png' | relative_url }}" alt="CAD isometric of the full assembled vehicle from a high front-quarter angle. Two side panels, four wheels, central cabin with bevel gear visible inside.">
        <figcaption>Assembled isometric — front-quarter view. The differential sits centred under the cabin opening.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/cad-iso-alt.png' | relative_url }}" alt="Second CAD isometric of the assembled vehicle from a different angle, showing the rear three-quarter view with the rear wheel pair and the back edge of the side panels.">
        <figcaption>Rear-quarter view. The rear shaft pad on the side panel is visible at lower right.</figcaption>
      </figure>
    </div>

    <p class="prose"><a href="{{ '/drawings/' | relative_url }}">All seven drawing sheets →</a> &nbsp;·&nbsp; <a href="{{ '/parts/' | relative_url }}">Full parts inventory →</a> &nbsp;·&nbsp; <a href="{{ '/process/' | relative_url }}">Print and assembly photo log →</a></p>
  </div>
</section>

<section id="dimensions" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="06" label="Dimensions" title="CAD model versus printed part." sub="Every printed feature was measured with calipers and compared back to the design value. Eleven features, one above 5 % error, three above 3 %. The bores shrink. The thickness over-extrudes. The outer dimensions hold." %}

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
                <th class="num">Δ (in)</th>
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
                <td data-label="Δ (in)" class="num">{{ r.delta_in }}</td>
                <td data-label="% error" class="num">{{ r.error_pct }}%</td>
              </tr>
              {% endfor %}
            </tbody>
          </table>
        </div>

        <p class="note">Threshold bands: ≤ 1.0 % acceptable, 1.0–3.0 % review, &gt; 3.0 % critical (left-margin marked). {{ site.data.dimensions.method.text }}</p>
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

    <p class="prose">PLA shrinks circular features more than rectangular ones — the bores all came out small, the outer length and height all came out close. The thickness ran the other way (over-extrusion at the wall) and is the only feature above 5 % error. None of the deviations forced a redesign; three of them (wheel bore, gear bore, hullside shaft hole) forced a hand-ream pass after print.</p>
  </div>
</section>

<section id="process" class="section">
  <div class="wrap">
    {% include section-header.html num="07" label="Print and assembly" title="Seven hours on the printer, eighteen at the bench." sub="The print is the easy part. The bench work is dominated by track welding — 148 links and 150 PLA rivets, every joint melted with a soldering iron." %}

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
        <h3>Print time — Bambu Lab</h3>
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
        <h3>Assembly time — by phase</h3>
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

    <p class="prose">Track welding ate the bench. 148 links plus 150 rivets is 298 small joints. Each rivet sits in two link holes; you push it through, hold it with one hand, and tap the head with the soldering iron until the PLA mushrooms. It takes about a minute per rivet once you have the rhythm; the first dozen take three.</p>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/slice-cabin.jpg' | relative_url }}" alt="Bambu Studio screenshot showing the central cabin part placed flat on the build plate. Slicing result panel reads 45.94 m of filament, 139.21 g, 3 hours 7 minutes model time, 3 hours 24 minutes total.">
        <figcaption>Central cabin slice. 139.21 g, 3 h 7 m model time on the Bambu.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/slice-hullside.png' | relative_url }}" alt="Bambu Studio screenshot of a hullside panel placed flat on the build plate. Slicing panel reports 23.51 m, 71.24 g, 1 hour 27 minutes model time.">
        <figcaption>Hullside slice. 71.24 g, 1 h 27 m. Two of them per build.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/slice-wheel.jpg' | relative_url }}" alt="Bambu Studio screenshot of a single drive wheel placed flat on the build plate. Slicing panel reports 1.67 m, 5.07 g, 9 minutes 20 seconds model time.">
        <figcaption>One wheel. 5.07 g, 9 m 20 s. Eight of them per build, batched.</figcaption>
      </figure>
    </div>

    <div class="cols cols--3">
      <figure class="figure">
        <img src="{{ '/assets/images/electronics-bench.jpg' | relative_url }}" alt="Top-down photo of the assembled cabin during electronics fit-up. Black power bank on the left, NEMA 17 stepper centered with bevel pinion on its shaft, white spider gears, breadboard with TB6612 driver below, jumper wires running between.">
        <figcaption>Cabin during electronics fit-up. The bevel pinion is already on the motor shaft; the differential carrier sits below.</figcaption>
      </figure>
      <figure class="figure">
        <img src="{{ '/assets/images/track-detail.jpg' | relative_url }}" alt="Close-up of a yellow drive wheel meshing with the printed track. Track links are red and blue PLA, joined by black rivets. The wheel teeth slot into the track-link recesses.">
        <figcaption>Drive wheel meshing the track. Square cutouts on the wheel rim engage the link teeth.</figcaption>
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
    {% include section-header.html num="08" label="Filament and cost" title="One spool of PLA. Twenty dollars. Zero waste." sub="The whole build prints from approximately one kilogram of PLA. No supports, no purge towers, no failed prints. Mass and cost broken down by part group below." %}

    {% assign f = site.data.filament %}
    <div class="stat-band">
      <div class="stat-band__item">
        <div class="stat-band__label">Total filament</div>
        <div class="stat-band__value">~{{ f.total_mass_g }} g</div>
        <div class="stat-band__sub">approximately one spool of PLA</div>
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

        <h3>The calculation</h3>
        <div class="calc">cost = (m_part + m_supports + m_purge) × (price_per_kg / 1000)
<br>
<br><strong>Total mass:</strong>  990 g
<br><strong>PLA price:</strong>   $20.00 / kg  =  $0.020 / g
<br><strong>Total cost:</strong>  990 g × $0.020/g  =  <strong>$19.80</strong>
<br>
<br><strong>Waste:</strong>       0 g supports + 0 g purge + 0 g failed  =  <strong>0 g  →  0 %</strong></div>
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
    {% include section-header.html num="09" label="Reflection and future" title="What didn't work. What I'd change. What I learned." sub="The vehicle drives. It also drifts toward one side, runs through tensioner adjustments faster than expected, and would not survive an hour on a hard floor. Everything below is honest." %}

    <div class="reflect">
      <div class="reflect__group">
        <h3>What didn't work the first time</h3>
        <p>The first hull layout drove the rear wheel pair. The differential was at the back of the cabin and the side gears had to push torque through the long shafts under load. Moving the drive forward shortened the load path; the bracket now sits where the cabin is widest.</p>
        <p>The first drivetrain used a fixed bevel reduction — one input, one shaft, two slip-fit wheels. It rolled in a straight line, then wound up against itself the moment a track caught a lip. Replacing the fixed pair with a true differential (two side gears, two spider gears, a carrier) gave the two outputs independent speed.</p>
        <p>Three printed bores came out small. The wheel bores were 6.00 % under (Ø0.282 in vs Ø0.300 in design). The hullside shaft holes were 4.67 % under. The bevel-gear bores were 4.00 % under. All three got reamed by hand during the print-cleanup phase. None of them came out of the printer ready to use; that should have been planned in from the start.</p>
        <p>One side of the track came out looser than the other. Small dimensional drift between the two link batches added up across the loop length. A printed tensioner — a flat tongue against the inside of the loop — took up the slack. The fix works, but the tensioner is a part the design didn't plan for; tighter batch-to-batch control would prevent the need for it.</p>
      </div>

      <div class="reflect__group">
        <h3>What I'd do differently next build</h3>
        {% for f in site.data.future %}
        <h4>{{ f.heading }}</h4>
        <p>{{ f.body }}</p>
        {% endfor %}
      </div>

      <div class="reflect__group">
        <h3>What I learned</h3>
        <p>The clear lesson is on tolerances: PLA shrinks circular features and over-extrudes flat walls, and the design has to plan for both. The clearance-fit bores should have been designed at Ø0.318 in if the printed result needed to be Ø0.300 in. Knowing the direction PLA moves is half the work; the other half is committing to that direction in the model instead of reaming after print.</p>
        <p>The other lesson is on motors and steering: a single drive source plus a passive differential teaches the differential, but it doesn't make a useful vehicle. Two motors and a closed-loop heading reference is where this build wants to go next. The hardware path is clear; the work is the controller.</p>
        <p>The third, smaller lesson is on assembly time. The print plan accounted for hours on the printer; the welding plan didn't account for the eight bench hours of soldering-iron work. The next plan budgets the assembly time honestly, because that's where the schedule actually sits.</p>
      </div>
    </div>

    <figure class="figure figure--inset" style="margin-top: 3rem;">
      <img src="{{ '/assets/images/tensioner.jpg' | relative_url }}" alt="Close-up of one corner of the hull showing a printed tensioner — a flat blue tongue projecting outward — pressing against the inside of the track loop to take up slack.">
      <figcaption>The blue tongue is the printed tensioner that took up slack on the looser of the two track loops.</figcaption>
    </figure>
  </div>
</section>

<section id="references" class="section section--soft">
  <div class="wrap">
    {% include section-header.html num="10" label="References" title="Sources used in the build." sub="Hardware references for the driver and the stepper library. A textbook reference for tracked-vehicle steering theory. Software documentation for Inventor and Bambu Studio. A historical reference for the hull silhouette." %}

    <ol class="refs">
      {% for r in site.data.references %}
      <li>
        {{ r.citation }}
        <span class="used-for">Used for: {{ r.used_for }}</span>
      </li>
      {% endfor %}
    </ol>
  </div>
</section>
