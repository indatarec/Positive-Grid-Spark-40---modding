# Positive Grid Spark 40 - Modding Tutorial

The Spark 40 is a 40-Watt Smart Guitar Amp & Bluetooth® speaker made by Positive Grid.

It has huge potential for improvement. In terms of audio quality and raw power, it can easily outperform the Spark 2 and many competing models.

There is already an excellent hardware teardown and analysis of the amp available on Hackaday:

https://hackaday.io/project/174163-positive-grid-spark-40-teardownmods

This guide is an addition to that article and contains my own findings and modifications.

There are two main motherboard revisions found in the Spark 40:

- **(Old)** `Jamup 2019.11.22 PN: ECB00511`  
  Found in Spark 40 units with serial numbers up to `S040C6xxxxxx`

- **(New)** `Jamup v1.2 20.12.18 PN: ECB00888`  
  Found in Spark 40 units with serial numbers starting from `S040C9xxxxxx`

![porownanie](https://github.com/user-attachments/assets/95ed6be3-975b-465d-809c-fa2ed36fcda1)

Both revisions produce similar audio quality and both can be modified, but the older board has a better analogue audio path and also supports adding an additional 50W output stage.

I marked the areas that require modification.

---

# Mods

There are several modifications that can significantly improve the Spark 40.

Recommended mods:

- **Bass Sock Mod** — recommended for everyone because it costs nothing.
- **Op-Amp Replacement + Full-Range Speaker Replacement** — these noticeably improve the Spark 40 audio quality and make it, in my opinion, the best-sounding Positive Grid amp.

---

## Bass Sock Mod

**Complexity:** Very low

**Effect:** Reduced bass response, highly noticeable

The front grill is mounted using Velcro tape. Simply remove the grill and place a piece of cloth, foam, or a sock into the bass reflex port.

Result: less excessive bass and a tighter sound.

![bass_mod](https://github.com/user-attachments/assets/1436d659-974c-4d49-9303-d2c6e0333756)

---

## Full-Range Speaker Replacement

**Complexity:** Low

**Effect:** Clearer tones, especially in higher frequencies, with improved audio dynamics

The Spark 40 uses 10 cm / 4" speakers. In my opinion, the stock speakers are mediocre at best.

I replaced them with:

- JBL Stage 1 42F
- JBL Stage 2 45F

Both produce a much clearer and crisper sound. Combined with the op-amp mod, they completely change the overall audio character of the Spark 40.

This modification is easy to perform because the speakers use quick connectors and are not soldered directly to the board.

![speakers_mod_small](https://github.com/user-attachments/assets/a86b9bbf-1ec5-4e8a-a180-3db1e3f67a32)

---

## Op-Amp Replacement (MUST-HAVE MOD)

**Complexity:** High

**Effect:** Eliminates unnecessary noise, removes white noise and crackling, improves guitar audio quality, and removes the "bass blanket" effect on guitar input

The Spark 40 uses a 3Peak TP2582 op-amp in a TSSOP-8 package for guitar signal amplification.

This is one of the weakest points of the amp because the IC is prone to failure.

If your Spark 40 suddenly stops producing guitar sound or starts generating strange noises that were not present before, the TP2582 is likely damaged.

There are not many drop-in TSSOP-8 replacement op-amps available. The best replacement I found is the Texas Instruments `TL072CPWR`.

It is reliable, inexpensive (around $1 on AliExpress), and provides a very noticeable improvement in sound quality.

If you compare two Spark 40 amps side by side — one stock and one modified with the TL072CPWR — the difference is immediately noticeable.

The TL072CPWR also performs better thanks to its lower noise and higher input impedance characteristics, which are especially important for guitar signals:

https://samsontech.com/blog/whats-a-hi-z-input-and-why-does-it-matter/

After replacing both the op-amp and the speakers, the Spark 40 sounds significantly better than the Spark 2.

With advanced soldering skills, the op-amp can also be replaced with even better chips such as:

- NE5532
- OPA2134

However, these are not commonly available in TSSOP-8 format, so adapters or additional work may be required.

This mod requires a hot-air soldering station and solid soldering skills.

![opamp_old_small](https://github.com/user-attachments/assets/f74ee7d3-a6ee-404a-ad0f-9f74cf2fe5dd)
![opamp_new_small](https://github.com/user-attachments/assets/bd92485f-a652-427e-839f-77424176f794)

Very high-voltage active pickups (such as EMG 18V/24V mods) can sometimes damage the original guitar op-amp inside the Spark 40.

The TL072 can tolerate much higher input offset voltages, making it far more reliable in those scenarios.

In my opinion, this is a must-have modification if you use heavily overvolted active pickups.

<img width="775" height="804" alt="ti opmap" src="https://github.com/user-attachments/assets/9593739c-f43b-45a8-a47a-aa561ca399d2" />

---

## 70W Mod

**Complexity:** Very high

**Effect:** More power and significantly higher output volume

The Spark 40 uses the `TPA3116D2` amplifier chip (50W).

By replacing it with the `TPA3156D2`, the amp output can be increased to around 70W.

This modification requires advanced soldering skills.

You do not need to upgrade the heatsink because the TPA3156D2 is more power-efficient at lower volumes. At maximum output both chips consume similar power, but the TPA3156D2 delivers noticeably higher volume.

The difference becomes immediately obvious because the volume potentiometer becomes far more sensitive.

After replacing the amplifier chip, I strongly recommend performing the **Gain Abuse Mod** described below, because the TPA3156D2 triggers the `FAULTZ` signal more frequently than the original amplifier.

![amp1_small](https://github.com/user-attachments/assets/22d1942c-cab6-453e-bbe3-c35ec7d85289)
![amp2_small](https://github.com/user-attachments/assets/eff870a7-577d-46d8-963e-5de3ea61f26e)
![amp3_small](https://github.com/user-attachments/assets/0c6446f5-40f6-4cf2-9efe-4e6d813974de)

---

## Capacitor Mod

**Complexity:** Medium

**Effect:** Improved stability and long-term reliability

This small modification improves long-duration stability.

Some Spark 40 units begin producing crackling sounds — or lose audio entirely — after running continuously for several hours.

The capacitor `C114` (`100uF 35V`) located near the amplifier heatsink is often the cause.

You do not need to increase its capacitance. Simply replacing it with a higher-quality capacitor is enough.

After this modification, the Spark 40 can run continuously without issues.

![cap1_small](https://github.com/user-attachments/assets/67d0eb2c-6cee-4157-9855-010f0407a53f)
![cap_mod_small](https://github.com/user-attachments/assets/0ca9b960-b6d9-46cf-a95e-8988a80623a2)

---

## Gain Abuse Mod — FAULTZ Disable

**Complexity:** Medium

**Effect:** Allows the amplifier to handle extremely high-gain signals and overdriven pickups more reliably

The amplifier chip includes a pin called `FAULTZ`.

Normally this pin is used for reporting faults such as:

- Over-temperature
- DC detection
- Open drain conditions

Temperature itself is usually not a problem because the heatsink keeps the amplifier below approximately 70°C.

However, the `FAULTZ` signal can sometimes trigger when using very high-gain pickups or heavily overdriven signals. When this happens, the Spark MCU briefly shuts down audio processing, causing short audio dropouts.

The harder the signal clips, the more frequently these shutdowns occur.

Newer Spark models allow this protection behavior to be adjusted through the app using "Hi-Z Mode", but on the Spark 40 this modification must be done manually.

### Older Spark 40 PCB

To disable the `FAULTZ` signal on the older PCB revision, simply bridge points `T67` and `T68`.

![faultz](https://github.com/user-attachments/assets/90a3946b-b8d9-4e58-899d-71832a0fc660)

### Newer Spark 40 PCB

On the newer PCB revision, `T67` and `T68` are located far apart.

- `T68` is near the MCU
- `T67` is located under the TPA3116D2 heatsink

The easier solution is to connect pin 3 of the TPA3116D2 directly to ground.

This modification is practically required for stable operation after performing the 70W mod.

---

## Bluetooth Mod

This involves replacing the Bluetooth module and antennas with higher-quality alternatives.

To be continued...

---

## Additional 50W Audio Output

**Complexity:** Very high

**Effect:** 50W internal speakers + 50W external passive speaker output

The Spark 40 was originally designed as a 100W (or even 120W) platform, and this mod unlocks much more of its original potential.

This modification is only possible on the older motherboard revision:

`Jamup 2019.11.22 PN: ECB00511`

Found in Spark 40 units with serial numbers up to `S040C6xxxxxx`.

To be continued...
