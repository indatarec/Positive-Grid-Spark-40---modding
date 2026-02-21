# Positive-Grid-Spark-40---modding
Positive Grid Spark 40 modding 

Spark 40 is 40-Watt Smart Guitar Amp & Bluetooth® Speaker from Positive Grid.
It has huge potential for improvement. In terms of audio quality and raw powercan easily bypass Spark 2 and other brand models.
There is an excellent hardware analysis of this amp on hackday.io:
https://hackaday.io/project/174163-positive-grid-spark-40-teardownmods
This is an addition and my own findings to the one above.

There are two motherboards seen in Spark 40:
- (old) Jamup 2019.11.22 PN: ECB00511 / Spark 40 with serial numbers up to S040C6xxxxxx
- (new) Jamup v1.2 20.12.18 PN: ECB00888 / Spark 40 with serial numbers from S040C9xxxxxx
[picture]
Both produce similar quality audio and both can be modded, but older board has better analog audio route and option to add additional 50W active output. I marked the area which need to me modded.

# MODS
There are several mods, which can improve its audio quality. I will grade them in terms of effect on audio.


# Bass decrease - sock mod
Complexity: very low
Effect: less bass, very noticable

# full range speakers replace 
Complexity: low
Effect: Much more clear tones, especially in higher frequency. Change in dynamic of audio.

Spark 40 uses 10cm / 4" speaders. They are good 


# op-amp replace (MUST HAVE MOD!)
Complexity: high
Effect: all unnecesary noices are gone, no more white noise or cracking sounds, gain in guitar audio quality

Spark 40 uses 3Peak TP2582 opamp in TSSOP8 package for guitar sound amplification. This is the weakest point in the amp since this IC is very faulty. If your Spark 40 stoped producing guitar sound or there are noises that you have not heard before, this probably means that TP2582 is dead already. There are not many TSSOP8 opamps on market which are drop-in replacements. The best one I have found is Texas Instruments TL072CPWR. It is reliable and because It costs 1$ on Aliexpress and I would say it is first mod that makes noticable difference. If you put two Spark 40, where one has TL072CPWR, you will notice the difference right away. After changing opamp and replacing speakers or full range ones, Spark 40 sounds way better than Spark 2.

TP2582-TSR na niezawodne TL072CPWR

# 70W mod
wymiana wzmacniacza TPA3116D2 (50W) na TPA3156D2 (70W)
