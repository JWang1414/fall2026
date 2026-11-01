# 9:28 Arrival
Last time I spent a good chunk of my time taking measurements of event 1 (from the lab manual) in Traxis. I had to get this done in order to analyze the data for today.
- Originally I wanted to analyze the measurements I had already taken from other events, but it turns out those are poor examples

Today, I would like to make good progress on the preliminary tasks to verify my knowledge while I can speak with my TA and supervisor. Once this is done, I will (hopefully) try to complete my analysis of event 1.

Over the reading week next week, I will take measurements of event 2. Then when I come in on day 6, I am prepared to complete that analysis.
## Preliminary investigations
Previously, I have spent some time identifying:
- Strong interactions
- Delta-rays
- Electron spirals
These are relatively easy to identify inside the chamber.

![[Pasted image 20261023095457.png]]
An example of what appears to be a charged particle decay in the chamber. 10 164 0877, rake 4. The charged particle is curving upwards, but they appear to be moving rightward in the chamber, implying that they are probably positively charged, fitting the description of the $\pi^+$ decay.

Roughly speaking, based on figure 1, the range of the track left by the muon here is so short because the momentum is also very small. Overall, this makes a lot of sense. The $\pi^+$ is moving quite slow by this point, it may even be at rest. The momentum carried by the muon is therefore entirely "provided" by the $\nu$.
- Basically, it's moving slow, and that makes sense for a number of reasons

Here are a few other possible examples:

![[Pasted image 20261023100816.png]]
20-254-0822, rake 14

![[Pasted image 20261023100841.png]]
20-254-0821, rake 6
# 10:26
Discussion with supervisor
- Preliminary is important, but try to analyze the events as soon as possible
- The charged particle decay and $\gamma$ conversions that I picked out this lab and the previous are confirmed to be correct identifications
	- The first candidate is very characteristic with the spiral
	- The other two that I picked out might not be decays into positrons, and instead might decay into something else. Just based on the shape of the tracks (no spiral)
- Most importantly, I was also taught how to read Figure 1 in the lab manual

We begin with the axis. On the right-side is $dE /dx$, which in English is the change in energy for some propagation distance inside the bubble chamber. This change in energy is what we visually register as the optical density/opacity. A higher $dE /dx$ corresponds with a larger optical density.
- We are lucky that the units are in hydrogen, which is what our bubble chamber is filled with

On the left-side, we have the range, so the distance we might expect a particle to travel inside the bubble chamber. The corresponds to the length of the tracks inside the chamber. So if we have a track that traveled some distance $r$, then if we know the momentum, we can use this side to try and reduce the possibilities down to just a few.

On the $x$-axis, we have the momentum. This is simply the momentum that is measured using Traxis.

Now, the dotted lines on the plot correspond with the right-axis, and the solid lines correspond with the left-axis. So solid lines tell us how far we might expect some particle in the bubble chamber to propagate with some momentum. The dotted lines tell us what optical density we might expect for some particle at some momentum
- One might see, for example, that $K$ and $p$ tend to have much darker tracks than $\mu$ and $\pi$. (Because they are heavier)
- Furthermore, if we have some track that goes 0.10 cm at 80 MeV/c, then it's most likely that the particle is probably a $p$ or $\Sigma$.
# 11:05
Discussion with TA
- It is possible to measure distances in the tank with Traxis, but there might be something in the lab manual telling me the distance for each rake
- When analyzing event 1, try to keep in mind the conserved quantities like charge. However remember that strangeness might not be conserved.

Now that I have spent some time on the preliminary investigations. I will begin to try my hand at event 1.

Just based on the diagram provided in the lab manual, and visually looking at the event in the chamber, I can tell a few initial things:
- The collision between the $\pi^+$ and $\pi$ have produced 2 positively charged particles, and 2 neutral particles
- Both neutral particles decay into at least one positive and one negative particle.
- The top particle, associated with tracks 5-6, is heavier. I can tell because the tracks it leaves behind are much darker
- You may also confirm that this is neutral particle decay, because it does not have the 0 degree vertex characteristic of $\gamma$ conversion.

- Spending some time porting my number to a spreadsheet
- Calculating parallel and perpendicular momenta
# 11:56 End

# Reading week
Measuring event 2 before my next session.

Notes:
- Measurements will be taken from the bottom up. Measurements of the secondary decayed particles will be listed after the initial ones.
- It is challenging to find the kink based on the curvature of the track (kink highlighted in the manual). I will instead use the drop in optical density as an indicator
- Smudged on the tank might make computer generated measurements of the optical density less reliable
- All angles are relative to the initial angle from the incoming $\pi^+$ particle

(Incoming)

Track Momentum: 5376.02899 +/- 1400.46591 (Stat) +/- 407.27492 (Cal) [MeV/c]
Track Momentum: 9325.27851 +/- 7480.11732 (Stat) +/- 706.46049 (Cal) [MeV/c]

(Bottom)

Track Momentum
	114.90958 +/- 5.65105 (Stat) +/- 8.70527 (Cal) [MeV/c]
	119.84456 +/- 4.29780 (Stat) +/- 9.07913 (Cal) [MeV/c]
Track Length (cm)
	12.25839 +/- 0.92867 [cm]
	11.72523 +/- 0.88828 [cm]
Opening Angle:
	201.19509 +/- 3.18389
	198.07928 +/- 3.18389
Optical density:
	259.73894 +/- 191.74179 [1/cm] (with dL=1.0)
	425.42495 +/- 191.88846 [1/cm] (with dL=2.0)
	588.93461 +/- 192.76505 [1/cm] (with dL=3.0)
	751.80606 +/- 195.01566 [1/cm] (with dL=4.0)
	912.75037 +/- 193.58776 [1/cm] (with dL=5.0)
	1069.49844 +/- 198.25477 [1/cm] (with dL=6.0)
	1226.27722 +/- 198.18210 [1/cm] (with dL=7.0)
	1377.39361 +/- 203.02274 [1/cm] (with dL=8.0)
	1529.41566 +/- 204.65154 [1/cm] (with dL=9.0)
	1673.62682 +/- 207.62004 [1/cm] (with dL=10.0)
- I tried to minimize the effect of the kink, but I don't really know where it is

Track Momentum: 1209.14542 +/- 79.21421 (Stat) +/- 91.60193 (Cal) [MeV/c]
Track Momentum: 580.74125 +/- 112.37212 (Stat) +/- 43.99555 (Cal) [MeV/c]
Track Length (cm): 17.22976 +/- 1.30529 [cm]
Track Length (cm): 11.24089 +/- 0.85158 [cm]
Opening Angle: 194.10039 +/- 2.02746
Opening Angle: 191.57443 +/- 2.02746
Optical density: 257.54889 +/- 183.70930 [1/cm] (with dL=1.0)
Optical density: 422.21426 +/- 183.46706 [1/cm] (with dL=2.0)
Optical density: 585.79624 +/- 182.44214 [1/cm] (with dL=3.0)
Optical density: 746.73254 +/- 183.20118 [1/cm] (with dL=4.0)
Optical density: 904.31441 +/- 185.01812 [1/cm] (with dL=5.0)
Optical density: 1060.32331 +/- 185.14596 [1/cm] (with dL=6.0)
Optical density: 1210.81030 +/- 186.93062 [1/cm] (with dL=7.0)
Optical density: 1357.62512 +/- 188.28972 [1/cm] (with dL=8.0)
Optical density: 1499.53142 +/- 191.31807 [1/cm] (with dL=9.0)
Optical density: 1639.18740 +/- 195.43863 [1/cm] (with dL=10.0)

(Top)

Track Momentum: 836.09809 +/- 114.40550 (Stat) +/- 63.34076 (Cal) [MeV/c]
Track Momentum: 773.30629 +/- 45.12470 (Stat) +/- 58.58381 (Cal) [MeV/c]
Track Length (px): 1046.60235 [px]
Track Length (cm): 12.43364 +/- 0.94194 [cm]
Opening Angle: 166.66430 +/- 0.28695
Opening Angle: 164.04165 +/- 0.28695
Optical density: 257.53043 +/- 180.88340 [1/cm] (with dL=1.0)
Optical density: 424.89525 +/- 183.98735 [1/cm] (with dL=2.0)
Optical density: 591.67532 +/- 182.79688 [1/cm] (with dL=3.0)
Optical density: 753.37429 +/- 180.29813 [1/cm] (with dL=4.0)
Optical density: 908.67285 +/- 175.80669 [1/cm] (with dL=5.0)
Optical density: 1056.55572 +/- 171.58804 [1/cm] (with dL=6.0)
Optical density: 1195.56261 +/- 167.24668 [1/cm] (with dL=7.0)
Optical density: 1324.47858 +/- 164.84969 [1/cm] (with dL=8.0)
Optical density: 1444.69772 +/- 165.48864 [1/cm] (with dL=9.0)
Optical density: 1559.36929 +/- 168.29110 [1/cm] (with dL=10.0)

Track Momentum: 67.10460 +/- 0.32565 (Stat) +/- 5.08368 (Cal) [MeV/c]
Track Momentum: 67.02236 +/- 0.86485 (Stat) +/- 5.07745 (Cal) [MeV/c]
Track Length (px): 484.75791 [px]
Track Length (cm): 5.75892 +/- 0.43628 [cm]
Opening Angle: 282.74327 +/- 0.04849
Opening Angle: 284.82731 +/- 0.04849
Optical density: 253.20635 +/- 175.03152 [1/cm] (with dL=1.0)
Optical density: 419.32671 +/- 177.25094 [1/cm] (with dL=2.0)
Optical density: 585.49405 +/- 179.59392 [1/cm] (with dL=3.0)
Optical density: 751.80985 +/- 183.33072 [1/cm] (with dL=4.0)
Optical density: 917.37727 +/- 178.78957 [1/cm] (with dL=5.0)
Optical density: 1074.06232 +/- 173.25599 [1/cm] (with dL=6.0)
Optical density: 1220.54802 +/- 164.80772 [1/cm] (with dL=7.0)
Optical density: 1351.00608 +/- 157.86208 [1/cm] (with dL=8.0)
Optical density: 1464.88765 +/- 153.20043 [1/cm] (with dL=9.0)
Optical density: 1565.44905 +/- 151.58495 [1/cm] (with dL=10.0)
- This top particle moves particularly slow. So the curve used to determine the momentum must be very short

(Additional decay particles)

Track Momentum: 214.14896 +/- 4.12205 (Stat) +/- 16.22341 (Cal) [MeV/c]
Track Momentum: 216.77926 +/- 4.52138 (Stat) +/- 16.42267 (Cal) [MeV/c]
Track Length (px): 699.53288 [px]
Track Length (cm): 8.31045 +/- 0.62958 [cm]
Opening Angle: 226.20272 +/- 1.44970
Opening Angle: 229.78347 +/- 1.44970
Optical density: 228.04172 +/- 164.76286 [1/cm] (with dL=1.0)
Optical density: 370.20244 +/- 159.51740 [1/cm] (with dL=2.0)
Optical density: 501.86658 +/- 147.04038 [1/cm] (with dL=3.0)
Optical density: 621.76664 +/- 135.31761 [1/cm] (with dL=4.0)
Optical density: 729.21133 +/- 122.81823 [1/cm] (with dL=5.0)
Optical density: 822.46693 +/- 115.52225 [1/cm] (with dL=6.0)
Optical density: 907.22438 +/- 112.29157 [1/cm] (with dL=7.0)
Optical density: 983.84419 +/- 111.60384 [1/cm] (with dL=8.0)
Optical density: 1055.04063 +/- 111.88041 [1/cm] (with dL=9.0)
Optical density: 1121.69425 +/- 112.75807 [1/cm] (with dL=10.0)
- One again, determining where this track starts is very difficult. (Obscure kink location)

Track Momentum: 765.36538 +/- 88.19470 (Stat) +/- 57.98223 (Cal) [MeV/c]
Track Momentum: 773.51875 +/- 2.85306 (Stat) +/- 58.59991 (Cal) [MeV/c]
Track Length (px): 872.88825 [px]
Track Length (cm): 10.36991 +/- 0.78560 [cm]
Opening Angle: 165.19276 +/- 0.22064
Opening Angle: 163.47616 +/- 0.22064
Optical density: 257.11188 +/- 181.26590 [1/cm] (with dL=1.0)
Optical density: 422.05553 +/- 178.35668 [1/cm] (with dL=2.0)
Optical density: 582.91874 +/- 170.16229 [1/cm] (with dL=3.0)
Optical density: 731.75735 +/- 155.72255 [1/cm] (with dL=4.0)
Optical density: 864.01593 +/- 143.52698 [1/cm] (with dL=5.0)
Optical density: 980.53176 +/- 132.80554 [1/cm] (with dL=6.0)
Optical density: 1081.11726 +/- 126.88435 [1/cm] (with dL=7.0)
Optical density: 1169.67626 +/- 124.70129 [1/cm] (with dL=8.0)
Optical density: 1250.04264 +/- 124.54626 [1/cm] (with dL=9.0)
Optical density: 1324.77393 +/- 127.22895 [1/cm] (with dL=10.0)
