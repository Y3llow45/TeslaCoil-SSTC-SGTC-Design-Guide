# Tesla Coil Build Guide

<img width="500px" height="500px" alt="unnamed" src="https://github.com/user-attachments/assets/609acf69-fad7-4179-8c92-6dba36bac857" /><img width="333px" height="500px" alt="Tesla3" src="https://github.com/user-attachments/assets/a86c80f4-a011-4549-9ea9-549d0b98234e" />

## Steps

1. **Safety First! Read everything! It's interesting!**

2. **Learn how Tesla Coils work - resonance of two coils!**

3. **Build Slayer Exciter → SGTC → SSTC → VTTC → DRSSTC → QCWSSTC → power a city wirelessly ( Nikola Tesla's biggest dream )**  

4. **Tune and Troubleshoot for huge sparks!**  

5. **Take pics and videos to impress your date!**

## ⚠️ Safety First - image by @DiodeGoneWild!

**WARNING: Building and operating any Tesla coil is EXTREMELY DANGEROUS!!!**  
**This guide is for educational and entertainment purposes only!!!**  
**You do everything at your own risk and responsibility!!!**

<img width="1393" height="783" alt="safety" src="https://github.com/user-attachments/assets/bda9af59-935f-4003-8ce2-de76c14dfd69" />

## ⚠️ Safety Simplified ( Dummy-Proof 💯 )

If you’re thinking “eh, it’ll be fine” — **Tesla Coils can kill you!**

- **Never touch anything while the circuit is powered on. EVER.**
- **Always discharge capacitors with grounded tools and gloves.**
- Wear **thick high-voltage insulating gloves, safety glasses, hearing protection**
- Wear a **respirator or gas mask for ozone and nitrogen oxides 😷☣️**
- Wear **non-conductive shoes - thick rubber soles**
- Work in a **well-ventilated area or outdoors**
- Keep a **Class C fire extinguisher - for electrical fires**
- **Never work alone**
- Keep flammable stuff (gasoline, paper, wood dust, curtains) far away.
- Ground the coil properly — but **never** use your house ground as the only return path.
- Turn off and unplug everything before adjusting or fixing anything.
- If you have a pacemaker, hearing aid, or any medical implant — stay far away from running Tesla coils.

If you’re not 100% sure what you’re doing, **don’t do it**. Start with a tiny Slayer Exciter on 12V instead of 5kW SGTC.

## Types of Tesla Coils

Tesla coils come in many topologies, each with different trade-offs in complexity, performance, sound, power handling, and efficiency. Below is a comparison table followed by detailed descriptions.  

**Difficulty levels** are based on electronics knowledge, tuning effort and component cost. <br>
**Efficiency** refers to *driver efficiency* (power delivered to the primary circuit) or *spark efficacy* (spark length/output per input watt) from community reports and tests. Overall Tesla coil efficiency to visible sparks is typically low (5–30%) due to corona losses and air ionization, but solid-state designs are significantly better than spark-gap ones. Exact numbers vary with build quality, tuning, and measurement method.

| Type | Description | Difficulty | Approx. Efficiency | Best For |
|-------------------------------|-----------------------------------------------------------------------------|----------------|-----------------------------|-----------------------------------|
| Spark Gap Tesla Coil (SGTC) | Classic design using a spark gap, high-voltage capacitor, and transformer (e.g., NST) to create loud, bright, high-power arcs. | 4/10 | Low (10–25%) | Traditional loud arcs, high power on a budget |
| Solid-State Tesla Coil (SSTC)| Uses MOSFETs/IGBTs for electronic switching instead of a spark gap. Cleaner, quieter, and more controllable. Supports interrupted (pulsed) or continuous wave (CW) mode. Includes high-efficiency Class-E variants. | 6/10 | Medium–High (30–70%) (up to Very High ~70–95% driver in optimized Class-E versions) | Reliable, quiet operation |
| Musical Tesla Coil (Zeusaphone) | SSTC or DRSSTC variant that modulates spark frequency/pulse width to play music (MIDI/interrupter). | 6/10 | Medium–High (30–95%) | Entertainment, shows |
| Dual Resonant Solid State Tesla Coil (DRSSTC) | SSTC with an extra primary capacitor for dual resonance. Handles massive peak currents for very long arcs. | 10/10 | High (50–95%+) | Maximum spark length, musical performance |
| Quasi-Continuous Wave DRSSTC (QCWDRSSTC) | DRSSTC variant with slowly ramped bus voltage for long, straight, sword-like sparks. | 10/10 | High (50–95%+) | Impressive long straight arcs, modern show coils |
| Vacuum Tube Tesla Coil (VTTC) | Uses powerful vacuum tubes (e.g., 811A, 833A, GU-81M) as the oscillator/switch in a Class-C Armstrong oscillator circuit. Often runs in continuous wave mode producing smooth, sword-like streamers. | 7/10 | Medium–High (40–70%) | Classic tube sound, continuous-wave plasma, retro builds |
| Slayer Exciter / Magnifier Circuit | Ultra-simple single-transistor self-resonant oscillator. Low-power, compact, often used for wireless bulb lighting. | 2/10 | Very Low (<25%) | Education, first project, demos |

### Detailed Breakdown

**Spark Gap Tesla Coil (SGTC)**  
Classic design: high-voltage transformer charges a capacitor until the spark gap fires into the primary. Produces loud, branching arcs.
- **Pros**: Robust, forgiving of bad tuning, raw power and thunderous sound.
- **Cons**: Noisy, high ozone, needs heavy HV transformers. 
- **Cool stuff**: Many restored antique rotary-gap builds still hit multi-meter arcs on a few kW.

<table>
  <tr>
    <td><img width="100%" height="300" alt="ezgif-40f1b95a1692ee23" src="https://github.com/user-attachments/assets/e9c60fc7-b0d4-4c0d-aa31-2f0c4246926c" />@Styropyro</td>
    <td><img width="400" height="300" alt="tesla501" src="https://github.com/user-attachments/assets/d9b474a2-50cd-4836-959e-4d56150e5a03" />@DiodeGoneWild</td>
  </tr>
</table>

**Solid-State Tesla Coil (SSTC)**  
Transistors (MOSFETs/IGBTs) replace the spark gap for clean resonant drive. Supports interrupted or CW mode.
- **Pros**: Quiet, runs on low DC voltage, easy pulse control. 
- **Cons**: Needs solid gate drive and protection.
- **Cool stuff**: Class-E versions run cool and efficient; simple upgrade from Slayer exciters.

<table>
  <tr>
    <td><img width="720" height="960" alt="wIMG_0393" src="https://github.com/user-attachments/assets/72352349-84f9-47c6-892b-f833b801d441" />Gao Guangyan</td>
    <td><img width="1105" height="989" alt="1814249525702" src="https://github.com/user-attachments/assets/c650c580-a4b2-4130-9abc-e5455683a2cc" />PCBWay</td>
  </tr>
</table>

**Musical Tesla Coil (Zeusaphone)**  
Modulated SSTC/DRSSTC that turns the arc into a plasma speaker via MIDI interrupter.
- **Pros**: Plays real music with the sparks.
- **Cons**: Extra MIDI/Arduino hardware required.
- **Cool stuff**: Sync multiple coils for shows; plasma speaker has almost zero distortion.

**Dual Resonant Solid State Tesla Coil (DRSSTC)**  
Adds primary capacitor for dual resonance and massive peak currents.
- **Pros**: Longest sparks per watt, full electronic control.
- **Cons**: Critical tuning and expensive IGBT protection needed.
- **Cool stuff**: Steve Ward designs started the modern hobby; record builds reach 4× secondary length.

<table>
  <tr>
    <td><img width="1422" height="800" alt="09nov2013_drsstc2_2" src="https://github.com/user-attachments/assets/32b96d58-b964-4273-9729-4f21539f1954" />Gao Guangyan</td>
  </tr>
</table>

**Quasi-Continuous Wave DRSSTC (QCWDRSSTC)**
DRSSTC with slow bus voltage ramping to create long, straight, sword-like sparks.
- **Pros**: Extremely impressive arcs
- **Cons**: Complex ramp control (buck converter or staccato) and precise tuning required.
- **Cool stuff**: Very beautiful long arcs.

<table>
  <tr>
    <td><img width="1520" height="1080" alt="123" src="https://github.com/user-attachments/assets/a3dcc196-14b0-430e-a9aa-b3035cf2479e" />@jmartis2 - btw this guy makes super cool videos</td>
    <td><img width="1520" height="1080" alt="124" src="https://github.com/user-attachments/assets/0a376099-dba3-4147-ae2b-6d9ee3d0cf50" />@Magneticitist | Most QCW look like this</td>
  </tr>
</table>

**Vacuum Tube Tesla Coil (VTTC)**  
Vacuum tubes (811A, 833A, etc.) in a Class-C oscillator for continuous-wave output.
- **Pros**: Smooth sword-like streamers, classic tube sound.
- **Cons**: High heat, needs filament supply and careful feedback tuning.
- **Cool stuff**: Retro feel with quiet, steady plasma; closest to Tesla’s original CW vision.

<table>
  <tr>
    <td><img width="510" height="383" alt="nahlad2_vttc11" src="https://github.com/user-attachments/assets/23fd5474-8fa4-489d-a5e0-fb1f03d2b932" />Jakub Tejiščák</td>
    <td><img width="510" height="383" alt="nahlad2_vttc14" src="https://github.com/user-attachments/assets/94121b07-9c4a-4488-bcf6-4bd56d206986" />Jakub Tejiščák</td>
  </tr>
</table>

**Continuous Wave Tesla Coil (CWTC)**  
SSTC-style driver run in true continuous mode with no interrupter. Produces steady flame-like plasma.  
- **Pros**: Beautiful silent continuous discharges for demos and artistic effects.  
- **Cons**: High continuous heat — often needs water cooling or huge heatsinks.  
- **Cool stuff**: Rare in modern builds; feels closest to Tesla’s original wireless power experiments.

<table>
  <tr>
    <td><img width="800" height="600" alt="sstc4_01" src="https://github.com/user-attachments/assets/82203d0f-fa23-4239-a4d6-e01f3ed77974" />danyk.cz</td>
    <td><img width="922" height="691" alt="sstc234" src="https://github.com/user-attachments/assets/dc06e8c6-c0cd-40b0-9b99-4544a6f73b02" />stirlingkit.com</td>
  </tr>
</table>

**Slayer Exciter / Magnifier Circuit**  
Single-transistor self-oscillating circuit with feedback winding.
- **Pros**: Runs on 9–24 V, no tuning needed, super simple.
- **Cons**: Very low power, not for big sparks.
- **Cool stuff**: Lights bulbs wirelessly from across the room; perfect first project.

<table>
  <tr>
    <td><img width="60%" height="888" alt="MusicalKit_build" src="https://github.com/user-attachments/assets/7501a599-45b6-4e6f-aa8a-f88c4d712158" /><br>leap.tardate.com</td>
  </tr>
</table>
---
