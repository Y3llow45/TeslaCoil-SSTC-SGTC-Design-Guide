# Tesla Coil Build Guide

## ⚠️ Safety First!

**WARNING: Building and operating any Tesla coil is extremely dangerous!!! This guide is for educational and entertainment purposes only!!! You do everything at your own risk and responsibility!!!**

- Mains voltage is dangerous!
- Tesla coils work with and produce extremely dangerous high voltage.
- Capacitors may remain charged to a dangerous voltage even after being disconnected from power.
- Risk of electric shock and death. Risk of fire. Risk of explosion.
- Risk of serious injury or burns.
- Electric arcs produce strong infrared, visible, and ultraviolet light — risk of serious eyesight damage and skin damage.
- Electric arcs produce toxic gases, especially nitrogen oxides and ozone.
- Tesla coils produce strong electromagnetic interference. This may be illegal in some regions.
- Electromagnetic radiation from Tesla coils may damage storage media and electronic devices, including life-support devices.
- Vacuum vessels may produce harmful X-ray radiation when exposed to high voltage from a Tesla coil, even at a distance (capacitively coupled).
- Do NOT open, repair, modify, or build any electric devices unless you are qualified for it.
- Do NOT attempt to do what you see in any videos or guides.
- The experiments shown in any Tesla coil videos are extremely dangerous! This guide and any related content are **not** instructions — they are for entertainment and educational purposes only.

**Never build or operate a Tesla coil without proper safety training, protective gear, and full understanding of the risks.**

## Types of Tesla Coils

Tesla coils come in many topologies, each with different trade-offs in complexity, performance, sound, power handling, and efficiency. Below is a comparison table followed by detailed descriptions.  

**Difficulty levels** are based on electronics knowledge, tuning effort and component cost. <br>
**Efficiency** refers to *driver efficiency* (power delivered to the primary circuit) or *spark efficacy* (spark length/output per input watt) from community reports and tests. Overall Tesla coil efficiency to visible sparks is typically low (5–30%) due to corona losses and air ionization, but solid-state designs are significantly better than spark-gap ones. Exact numbers vary with build quality, tuning, and measurement method.

| Type | Description | Difficulty | Approx. Efficiency | Best For |
|-------------------------------|-----------------------------------------------------------------------------|----------------|-----------------------------|-----------------------------------|
| Spark Gap Tesla Coil (SGTC) | Classic design using a spark gap, high-voltage capacitor, and transformer (e.g., NST) to create loud, bright, high-power arcs. | 4/10 | Low (10–25%) | Traditional loud arcs, high power on a budget |
| Solid-State Tesla Coil (SSTC)| Uses MOSFETs/IGBTs for electronic switching instead of a spark gap. Cleaner, quieter, and more controllable. Supports interrupted (pulsed) or continuous wave (CW) mode. Includes high-efficiency Class-E variants. | 5/10 | Medium–High (30–70%) (up to Very High ~70–95% driver in optimized Class-E versions) | Reliable, quiet operation |
| Musical Tesla Coil (Zeusaphone) | SSTC or DRSSTC variant that modulates spark frequency/pulse width to play music (MIDI/interrupter). | 6/10 | Medium–High (30–90%) | Entertainment, shows |
| Dual Resonant Solid State Tesla Coil (DRSSTC) | SSTC with an extra primary capacitor for dual resonance. Handles massive peak currents for very long arcs. | 9/10 | High (50–95%+) | Maximum spark length, musical performance |
| Slayer Exciter / Magnifier Circuit | Ultra-simple single-transistor self-resonant oscillator. Low-power, compact, often used for wireless bulb lighting. | 2/10 | Very Low (<25%) | Education, first project, demos |

### Detailed Breakdown

**Spark Gap Tesla Coil (SGTC)**  
The original “classic” Tesla coil invented by Nikola Tesla himself in the 1890s. A high-voltage transformer (often a salvaged neon sign transformer) charges a capacitor bank until the spark gap fires, releasing a massive pulse of energy into the primary coil. This creates the iconic loud, branching lightning-like arcs that defined early high-voltage demonstrations.  
- **Pros**: Extremely robust and forgiving of mistuning; delivers raw power and that unmistakable thunderous crack.  
- **Cons**: Produces ear-splitting noise, lots of ozone, and requires high-voltage AC input with heavy transformers.  
- **Cool stuff**: Many builders restore antique spark-gap coils from the early 1900s radio era — some still use original rotary spark gaps that spin at hundreds of RPM for the perfect rhythmic firing sound. Real-world examples have reached multi-meter arcs on just a few kW using simple garage parts.

**Solid-State Tesla Coil (SSTC)**  
Replaces the noisy spark gap entirely with fast-switching transistors (MOSFETs or IGBTs) driven at the exact resonant frequency of the secondary. The result is a clean, repeatable high-frequency drive that can be precisely controlled by simple electronics.  
- **Pros**: Runs on safe low-voltage DC (often 100–400 V), almost silent operation, and easy to add features like adjustable pulse timing.  
- **Cons**: Needs careful gate-drive design and over-current protection to keep the transistors alive.  
- **Cool stuff**: Includes high-efficiency Class-E variants that run surprisingly cool even at moderate power, and many modern SSTCs can instantly switch between interrupted bursts and true continuous-wave (CW) mode by simply disabling the interrupter — perfect for experimenting with steady plasma “flames.” Popular first solid-state project for builders moving beyond Slayer exciters.

**Musical Tesla Coil (Zeusaphone)**  
A modulated version of an SSTC or DRSSTC where an audio signal (often MIDI from a computer or keyboard) rapidly changes the pulse width or frequency. The plasma arc itself becomes the speaker, turning high-voltage electricity into audible music.  
- **Pros**: Turns your coil into a show-stopping performance piece — arcs literally play songs in real time.  
- **Cons**: Requires extra interrupter electronics (Arduino, dedicated MIDI boards, or even a simple 555 timer for basic tones).  
- **Cool stuff**: The plasma acts as a true “plasma speaker” with almost no distortion at high volumes. Famous builds have performed entire concerts, and some Zeusaphones sync multiple coils for stereo or even light-show effects using the same MIDI track.

**Dual Resonant Solid State Tesla Coil (DRSSTC)**  
The modern high-performance champion. It adds a resonant capacitor to the primary circuit so both primary and secondary rings perfectly in tune, allowing the inverter to dump enormous peak currents (often thousands of amps) in very short, controlled bursts.  
- **Pros**: Delivers dramatically longer sparks for the same input power and size than any other solid-state design; sounds and looks almost identical to a classic SGTC but with full electronic control.  
- **Cons**: Tuning is critical (JavaTC software is your best friend) and the expensive IGBT bricks need serious protection circuitry.  
- **Cool stuff**: Steve Ward’s original DRSSTC designs in the early 2000s sparked a worldwide hobbyist revolution. Record-breaking coils have produced sparks over 4× the secondary coil length (e.g., 53-inch arcs from a 13-inch secondary). Many top musical coils today are DRSSTCs because the huge energy transfer makes the music loud and crisp even outdoors.

**Continuous Wave Tesla Coil (CWTC)**  
An SSTC-style driver run in true continuous (non-interrupted) mode with no off-time between pulses. The output is a steady, non-pulsing RF field that creates smooth, flame-like corona or plasma rather than explosive sparks.  
- **Pros**: Produces beautiful, silent, continuous discharges perfect for scientific demos or artistic “plasma flames.”  
- **Cons**: Extreme continuous heat in the primary coil and transistors usually requires water cooling or massive heatsinks.  
- **Cool stuff**: True CW builds are rare gems in the hobby — one famous example is the “world’s first water-cooled CWTC” that keeps the primary coil submerged in flowing water to survive long runs. Tesla himself preferred continuous-wave excitation for his wireless power dreams, so these coils feel closest to his original vision.

**Slayer Exciter / Magnifier Circuit**  
The ultimate beginner’s “Tesla-coil-like” project — a single transistor (BJT or MOSFET) with a tiny feedback winding that self-oscillates at the secondary’s resonant frequency with almost zero tuning required.  
- **Pros**: Runs on 9–24 V batteries or a wall wart, super compact, and incredibly forgiving.  
- **Cons**: Very low power output and not suitable for big sparks or shows.  
- **Cool stuff**: Named after the online forum user “Slayer” who popularized the circuit in the early 2000s. It’s famous for wirelessly lighting fluorescent tubes, neon bulbs, and even LEDs from across the room — the perfect “wow” demo to show friends or students. Some wild pancake-style Slayer builds have even melted copper wire just for fun!

---

## Next Steps for This Guide (Suggestions)

This “Types of Tesla Coils” section is a perfect starting point for your GitHub repo’s README. Here’s what I recommend adding next (in logical order):

1. **Safety First!** (Critical — put this near the top of the main README)  
   - High-voltage dangers, RF burns, ozone, fire hazards, legal notes, and mandatory safety gear.

2. **How a Tesla Coil Works** (Theory)  
   - Basic resonant transformer explanation + LC resonance formula (use KaTeX).  
   - Coupling coefficient, Q-factor, and energy transfer.

3. **Choosing Your First Build**  
   - Recommendation flow-chart (e.g., “Start with Slayer Exciter → SSTC → DRSSTC”).

4. **Components & Tools**  
   - Shopping lists, suppliers (Mouser, Digi-Key, eBay), JavaTC calculator link.

5. **Build Guides** (with step-by-step MD pages or folders)  
   - Slayer Exciter (easiest)  
   - Mini SSTC  
   - Full DRSSTC (with UD2 driver)  
   - Musical add-on guide

6. **Tuning & Troubleshooting**  
   - Oscilloscope use, JavaTC examples, common failure modes.

7. **Advanced Topics**  
   - QCW (Quasi-Continuous Wave), VTTC (vacuum tube), large-scale coils, measurement techniques.

8. **Gallery / Video Embeds** + BOM templates + PCB files (Gerber downloads).

9. **Contributing & License** (MIT or similar for open-source hardware).


