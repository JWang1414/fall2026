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
