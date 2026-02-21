# Positive Grid Spark 40 - modding tutorial

Spark 40 is 40-Watt Smart Guitar Amp & Bluetooth® Speaker from Positive Grid.
It has huge potential for improvement. In terms of audio quality and raw powercan easily bypass Spark 2 and other brand models.
There is an excellent hardware analysis of this amp on hackday.io:
https://hackaday.io/project/174163-positive-grid-spark-40-teardownmods

This is an addition and my own findings to the one above.

There are two motherboards seen in Spark 40:
- (old) Jamup 2019.11.22 PN: ECB00511 / Spark 40 with serial numbers up to S040C6xxxxxx
- (new) Jamup v1.2 20.12.18 PN: ECB00888 / Spark 40 with serial numbers from S040C9xxxxxx

![porownanie](https://github.com/user-attachments/assets/95ed6be3-975b-465d-809c-fa2ed36fcda1)

Both produce similar quality audio and both can be modded, but older board has better analog audio route and option to add additional 50W active output. I marked the area which need to me modded.

# MODS
There are several mods, which can improve its audio quality. I recommend:
- "Bass sock mod" for everyone because it costs nothing. 
- "Op-amp replace" + "Full range speakers replace" which noticably improve Spark 40 audio quality and make it best sounding amp across all Positive grid ones.

## Bass sock mod
**Complexity:** very low

**Effect:** less bass, very noticable

Grill is mounted on velcro tape. Just take the grill and put something in the bass reflex hole. Effect - less bass.
![bass_mod](https://github.com/user-attachments/assets/1436d659-974c-4d49-9303-d2c6e0333756)

## Full range speakers replace 
**Complexity:** low

**Effect:** better clear tones, especially in higher frequency. Change in dynamic of audio.

Spark 40 uses 10cm / 4" speaders. They are medicore at most. I replaced them with JBL Stage 1 42F or JBL Stage 2 45F. Both produce much crispier sound and with op-amp mod totally change audio perception from Spark 40 amp. Mod is easy to perform, because speakers are not soldered and there are quick connectors to them.
![speakers_mod_small](https://github.com/user-attachments/assets/a86b9bbf-1ec5-4e8a-a180-3db1e3f67a32)


## Op-amp replace (MUST HAVE MOD!)
**Complexity:** high

**Effect:** all unnecesary noices are gone, no more white noise or cracking sounds, gain in guitar audio quality, no more bass-blanket oner guitar sound

Spark 40 uses 3Peak TP2582 opamp in TSSOP8 package for guitar sound amplification. This is the weakest point in the amp since this IC is very faulty. If your Spark 40 stoped producing guitar sound or there are noises that you have not heard before, this probably means that TP2582 is dead already. There are not many TSSOP8 opamps on market which are drop-in replacements. The best one I have found is Texas Instruments TL072CPWR. It is reliable and because It costs 1$ on Aliexpress and I would say it is first mod that makes noticable difference. If you put two Spark 40, where one has TL072CPWR, you will notice the difference right away. After changing opamp and replacing speakers or full range ones, Spark 40 sounds way better than Spark 2.

With some soldering skills op-amp can be replaced with much better NE5532 or OPA2134, but I have not seen them in TSSOP8 package. You need to have hot-air soldering station and some soldering sills to perform this
![opamp_old_small](https://github.com/user-attachments/assets/f74ee7d3-a6ee-404a-ad0f-9f74cf2fe5dd)
![opamp_new_small](https://github.com/user-attachments/assets/bd92485f-a652-427e-839f-77424176f794)

## 70W mod
**Complexity:** very high

**Effect:** MOAR POWAH!

Spark 40 uses TPA3116D2 (50W). We can almost double its power by replacing the amp to TPA3156D2 (70W). True soldering skills are needed. You do not need to change radiator, because using the same volume TPA3156D2 eats less power. At maximum volume they need the same power, but TPA3156D2 is almost twice as loud. Difference is most noticable, because you need to adjust volume potentiometer very carefully now.

wymiana wzmacniacza TPA3116D2 (50W) na TPA3156D2 (70W)
![amp1_small](https://github.com/user-attachments/assets/22d1942c-cab6-453e-bbe3-c35ec7d85289)
![amp2_small](https://github.com/user-attachments/assets/eff870a7-577d-46d8-963e-5de3ea61f26e)
![amp3_small](https://github.com/user-attachments/assets/0c6446f5-40f6-4cf2-9efe-4e6d813974de)

## Capacitor mod
**Complevity:** medium

**Effect:** a bit better scene, Spark 40 can play 24/7 after this

This is small mod that allows Spark 40 to play longer. Some amps after 3-4 hours can produce crackling sound or even no sound in speakers. The capacitor C114 (100uF, 35V) just near amp radiator is very weak and should be changed in this case. You do not need to change its capacity, just but better quality cap.
![cap1_small](https://github.com/user-attachments/assets/67d0eb2c-6cee-4157-9855-010f0407a53f)
![cap_mod_small](https://github.com/user-attachments/assets/0ca9b960-b6d9-46cf-a95e-8988a80623a2)


## Additional 50W audio out
**Complexity:** very high

**Effect:** 50W internal speakers + 50W external passive speaker. Spark 40 was designed to be 100W (or even 120W) amp and you can unleash its full power.

Mod possible only in old PCB Jamup 2019.11.22 PN: ECB00511 / Spark 40 with serial numbers up to S040C6xxxxxx. To be continued...
