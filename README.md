# Tesla Coil Build Guide

**Welcome to the Tesla Coil Builder's Guide!**  
This guide will help you build something great! <br>
**⚠️ High voltage is extremely dangerous — always prioritize safety!**

## Types of Tesla Coils

Tesla coils come in many topologies, each with different trade-offs in complexity, performance, sound, power handling, and efficiency. Below is a comparison table followed by detailed descriptions.  

**Difficulty levels** are based on electronics knowledge, tuning effort, component cost, and safety risks (Beginner = minimal experience needed; Advanced = strong high-voltage/electronics background required).  
**Efficiency** refers to *driver efficiency* (power delivered to the primary circuit) or *spark efficacy* (spark length/output per input watt) from community reports and tests. Overall Tesla coil efficiency to visible sparks is typically low (5–30%) due to corona losses and air ionization, but solid-state designs are significantly better than spark-gap ones. Exact numbers vary with build quality, tuning, and measurement method.

| Type                          | Description                                                                 | Difficulty     | Approx. Efficiency          | Best For                          |
|-------------------------------|-----------------------------------------------------------------------------|----------------|-----------------------------|-----------------------------------|
| Spark Gap Tesla Coil (SGTC)  | Classic design using a spark gap, high-voltage capacitor, and transformer (e.g., NST) to create loud, bright, high-power arcs. | 4/10 | Low (10–25%)               | Traditional loud arcs, high power on a budget |
| Solid-State Tesla Coil (SSTC)| Uses MOSFETs/IGBTs for electronic switching instead of a spark gap. Cleaner, quieter, and more controllable output. | 5/10   | Medium–High (30–70%)       | Reliable, quiet operation        |
| Musical Tesla Coil (Zeusaphone) | SSTC or DRSSTC variant that modulates spark frequency/pulse width to play music (MIDI/interrupter). | 6/10 | Medium–High (30–70%)       | Entertainment, shows             |
| Dual Resonant Solid State Tesla Coil (DRSSTC) | SSTC with an extra primary capacitor for dual resonance. Handles massive peak currents for very long arcs. | 9/10       | High (50–80%+)             | Maximum spark length, musical DRSSTC |
| Single Resonant Solid State Tesla Coil (SRSSTC) / Class-E | Simpler solid-state design (often Class-E amplifier) focused on high efficiency and clean sine-wave output. | 6/10   | Very High (70–95%+ driver) | Efficient, low-heat continuous runs |
| Continuous Wave Tesla Coil (CWTC) | Feedback-oscillator driven for steady (non-pulsed) oscillation. Produces continuous plasma rather than bursts. | 9/10       | High (40–80%)              | Steady flames, scientific demos  |
| Slayer Exciter / Magnifier Circuit | Ultra-simple single-transistor self-resonant oscillator. Low-power, compact, often used for wireless bulb lighting. | 2/10       | Very Low (<20%)            | Education, first project, demos  |
| Tesla Magnifying Transmitter (TMT) | Tesla’s original advanced design: primary + secondary + separate third “extra” resonator coil for extreme voltage magnification and wireless power experiments. | 10/10         | Potentially High (transmission-focused) | Wireless power research, historical builds |

### Detailed Breakdown

**Spark Gap Tesla Coil (SGTC)**  
The original “classic” Tesla coil. A high-voltage transformer charges a capacitor until a spark gap fires, dumping energy into the primary coil. Produces the iconic loud, branching lightning-like arcs.  
- **Pros**: Simple mechanics, very robust, impressive visual/sound output.  
- **Cons**: Noisy (spark gap), high-voltage input required, ozone/UV production, harder to control.  
- **Typical build cost**: Low–Medium (uses salvaged NSTs).  
- **Example power**: 1–10+ kW input possible.

**Solid-State Tesla Coil (SSTC)**  
Replaces the spark gap with transistors (MOSFETs or IGBTs) driven at the resonant frequency. Much quieter and more repeatable.  
- **Pros**: Lower noise, better control, runs on lower DC voltages.  
- **Cons**: Requires good gate-drive circuitry and protection.  
- **Common variants**: Half-bridge or full-bridge.

**Musical Tesla Coil (Zeusaphone)**  
A modulated SSTC or DRSSTC. An interrupter or audio signal varies pulse width/frequency to create audible tones in the arc plasma.  
- Often built as a DRSSTC for louder music.  
- Requires MIDI-to-interrupter electronics (e.g., Arduino or dedicated driver).

**Dual Resonant Solid State Tesla Coil (DRSSTC)**  
The modern “king” for big sparks. Adds a primary capacitor so both primary and secondary circuits resonate. Allows huge peak currents (hundreds to thousands of amps) in short bursts.  
- **Pros**: Longest sparks for given size/power, excellent musical performance.  
- **Cons**: Complex tuning (JavaTC calculator recommended), expensive IGBTs, needs robust protection.  
- Popular drivers: Steve Ward’s UD2.x series.

**Single Resonant Solid State Tesla Coil (SRSSTC) / Class-E**  
A streamlined SSTC (often single-ended Class-E amplifier). The primary is tuned as a single resonant circuit with careful component selection for zero-voltage switching.  
- **Pros**: Extremely efficient, runs cool, simple circuitry.  
- **Cons**: Lower peak power than DRSSTC.  
- Great for beginners moving beyond Slayer exciters.

**Continuous Wave Tesla Coil (CWTC)**  
Uses a feedback oscillator (or locked PLL) for non-pulsed, continuous RF output. Produces smooth, flame-like plasma rather than explosive bursts.  
- **Pros**: Silent, steady output.  
- **Cons**: Requires excellent heat sinking (often water-cooled for big builds); sparks are usually shorter than pulsed designs for the same average power.

**Slayer Exciter / Magnifier Circuit**  
The absolute simplest “Tesla-coil-like” circuit — usually a single BJT or MOSFET with feedback from the secondary. Self-oscillates with almost no tuning.  
- **Pros**: Runs on 9–24 V, lights fluorescent tubes wirelessly, perfect educational tool.  
- **Cons**: Very inefficient, low power, not a true high-performance Tesla coil.  
- Ideal first project.

**Tesla Magnifying Transmitter (TMT)**  
Nikola Tesla’s own advanced concept: a three-coil system (primary, secondary, and a separate “extra” or magnifying resonator coil). Designed for wireless power transmission with minimal radiation losses.  
- **Pros**: Can achieve extremely high voltages; historically significant.  
- **Cons**: Extremely difficult tuning, large size, safety concerns.  
- Modern replicas often focus on wireless power or ground-current transmission experiments.

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

## ⚠️ Safety First!

**WARNING: Building and operating any Tesla coil is extremely dangerous. This guide is for educational and entertainment purposes only. You do everything at your own risk and responsibility.**

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
