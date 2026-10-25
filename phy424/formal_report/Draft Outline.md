- Do not include an appendix
- 4-8 pages long. (Generally speaking) at most four figures and two tables
- Properly cite everything I do not own. Even in the draft
# Title
- Probably something about qualitative observations of solitons
# Abstract
- Length is capped at 600 words
# Introduction
- Background information. Motivation for my paper/study
- Necessary physics background. Formulae I will use, and the reader needs to understand the data/results/observations

Solitons are nonlinear singleton waves that propagate similarly to particles. They are very stable, and can travel long distances without breaking apart. Due to the similarities they share with particles, solitions can reflect off walls, collide with each other head-on, or one faster soliton can overtake a slower one while maintaining their structure. When solitons collide or overtake each other, there is a resulting phase shift. Larger solitons are taller, thinner, and faster than smaller solitons. This is how it is possible for one to overtake another.
- Most of this is theory, and should cite the lab manual

Given in the lab manual is this equation:
$$
	\frac{1}{c_{0}}h_{t} + h_{x} + \epsilon \left( \frac{3}{2H} \right) hh_{x} + \delta^{2}\left( \frac{h^{2}}{6} \right)h_{x x x} =0
$$
Which, in the shallow water limit collapses to:
$$
	\frac{1}{c_{0}} h_{t} + h_{x} =0 \implies h(x, t) = f(x-c_{0}t)
$$
So the wave corresponds with any shape $h(x, 0)=f(x)$ at $t=0$ that moves with a constant speed $c_{0}$. This is valid, for example, with tsunami waves, because their lateral extents is much greater than the depth of the ocean.
- There is dispersion when the shallow water limit is relaxed, especially when surface tension is reduced
- These equations have citations, but they all lead to dead links

The nonlinear PDE also has the soliton solution, the one that appears in this experiment:
$$
	h(x, t) = h_{0} \sech^{2}\left[ \frac{x-Ut}{w} \right]
$$
Where we have defined the amplitude $h_{0}$, speed $U$, and width $w$
$$
	U=c_{0}\left( 1+\frac{h_{0}}{2H} \right) \qquad w=2H\sqrt{ \frac{H}{3h_{0}} }
$$
Notice that $U\propto h_{0}$ and $w\propto h_{0}^{-1}$. This describes why largest solitions are always taller and thinner.

- During my lab, I study the behaviour of single solitons in a tank, to observe how closely they agree with theory (and the theoretical models of solitons)
- I make one attempt with soliton collisions, but this isn't a huge focus
- Observing how soliton theory breaks down in shallow water. What happens when the amplitude is significant in comparison to the water depth?

# Experimental Techniques
- Go through data collection mechanisms

Before filling the tank with water, the camera must be calibrated by placing a metre stick inside the tank. This will allow us to determine the cm to pixel ratio in the recording. Once this is done, the tank is filled with water, for my purposes, this is anywhere from 2-6 cm. To maximize the visibility, the water is dyed orange with red food colouring, and a white backlight is placed behind the water. This guarantees that the orange water stands out strongly against the white backdrop on camera.
- Remember to mention the camera model, and perhaps camera settings
	- The camera settings were important to minimize stuttering and consistency in the recording.
	- Changing the brightness and exposure improved visibility
	- Colour grades and FPS changes to remove flickering
	- Consistent FPS (120) allowed me the measure time in the recording
- The water was measured with a classical ruler
- The water tank is slightly tilted, resulting in water gathering on the side with the wavemaker

To collect a trial of data, the camera was set to record according to the above settings. Then, one wave could be sent from the wavemaker, with some specified displacement and acceleration. Continue recording until the desired data is collected. This may be until some number of reflections across the boundaries is completed, this may be after some amount of time has passed. Once the recording is stopped, each individual frame is saved as an image to be processed.
- In my lab report, the displacement and acceleration will often be reported like so: $(\text{displacement}, \text{acceleration})=(10, 100)$

- Explain how data was analyzed (referring to equations from the introduction)

Data processing is equivalent to processing several thousand frames, which is just a collection of images. To begin, the beginning of the dataset, before the soliton is on screen, is deleted to save space. Then, the images are all uniformly cropped, and converted to binary (black and white). It is much easier to fit a curve or measure binary values. In my case, each frame is treated as a data point, and the height of the water is plotted on a colourmesh. The resulting data essentially tell us the location of the solition as a function of time.
- Whenever the soliton disappears off to the left-side, that is the soliton moving off camera. Only the right side of the tank is recorded
- I fit a sech-squared function to my preliminary data, but this same function cannot be applied to my later analysis
- Most of my analysis, because I could not use any fitting functions, was qualitative. (Also because of time constraints) The colourmesh plots were invaluable for this purpose. I could see phenomona of interest, and I could confirm the shape and speed of larger solitons agreed with theory

# Observations (Results, Discussion, Analysis)
- Discussion of results. Compare with other observations. Why is this important?

When a single soliton is sent through the tank, the results agree closely with theory. As predicted, the wave exhibits a characteristic $\sech^{2}$ shape, while propagating no dissimilarly to a particle. The soliton has no trouble maintaining its shape upon reflecting from walls, but will, however, slowly dissipate with time. This dissipation highlights another key characteristic of solitons: larger solitons are taller, thinner, and faster.
- One can notice from the data that, as the soliton slows down, it will always widen out
- Smaller solitons that are sent through the tank also exhibit this behaviour. They are shorter, wider, and slower
- Perhaps there is something to be said about wave-particle duality here? It is interesting that the faster solitons have a more defined position (thinner), but the slower ones are wider and so less defined

Soliton theory states that, when two solitons collide, the structure of both solitons is maintained, but they will experience a $\pi /2$ phase shift. Physically, this manifests as a slight delay in the propagation of one soliton, but an acceleration for the other. I conducted a few two wave trials where I tried to have a faster soliton overtake a slower one, but I was unsuccessful in setting it up. I did manage to capture a few head-on collisions between two solitons, but the plots do not show a noticeable difference. Espectially not on the scale of what is shown in the manual.
- Overall, I would say that I was unable to confirm this phenomona
- I did not spend too much time studying this topic, so I guess it makes sense that I didn't make so much head way

In the shallow water limit, I find that basic soliton theory begins to break down. The solitons no longer resemble $\sech^{2}$ shapes, and, more interestingly, disperse upon reflecting off a wall. This dispersion is hinted at in the manual, which claims that water surface tension is responsible. To be specific, in the shallow water, solitons instead have a short head, and a long trailing tail. Then, after reflection, "shatter" into several smaller solitons, each of which will individually propagate along the tank. The original "head" soliton will remain the largest and fastest, but the trailing ones will be progressively smaller and slower.
- This is essentially a breakdown in soliton theory. The models provided in the manual are no longer reliable

One might initially suspect that the dispersion phenomona is an indication of a shift from the soliton regime to the more common sinusoidal wave regime. One may argue that the shallow water is instead just accelerating the decay from one regime to the other. To investigate this, I increased the water depth, and sent a number of waves through before allowing them propagate until the waves in the tank dissipated. In these cases, the solitons in the tank would simply decay smaller and smaller until eventually disappearing from the camera. I conclude that the soliton dispersion is not a consequence of a regime shift, but is instead a behaviour characteristic of solitons in shallow water.

However, among the previous trials, I noticed that larger solitons in the tank would exhibit the same dispersion behaviour present in shallow water. The amplitude of the soliton, however, had to be much larger than in the shallow water case for it to occur. This suggests that dispersion grows more apparent when the ratio between the amplitude $A$, and the water depth $H$, is large. That is, dispersion occurs when $A /H\to 1$.
- One may be curious as to what happens when $A /H\to \infty$, but, due to limitations in the setup, I was unable to test this. Furthermore, the experimental viability of this setup is questionable. Is it even possible for $A\gg H$? $H$ defines how much water is available, you might need more water in the wave than in the tank. Perhaps something closer to $A /H\to 2$ or some other constant is more reasonable
- While this answer *when* dispersion occurs, it does not tell us *why*. It must just be that the soliton is splitting into a number of smaller solitons. But it could also be that the soliton is interfering with the long tail it leaves in the water. One could try to experiment with this by allowing a shallow water soliton to propagate for a long distance without interaction, or having it bump into a shore to see if it'll split. Given the time and setup limitations, this was out of the scope of the lab

# Conclusions
- Brief overview of the major points
- Include main results. What are the major "take-aways"?

- Solitons are nonlinear waves that exhibit particle-like behaviour
- They are known to maintain their shape upon reflection with walls, and collisions with each other
- In this lab I confirm the basic theoretical predictions made in soliton theory regarding their shape, propagation speed, and behaviour upon reflection and collision
	- I was not, however, able to confirm that they experience a phase shift upon interaction with each other (overtaking, and head-on collison)
- When the amplitude of the solition is not significantly smaller than the depth of the water, $A /H\to 1$, solitons begin to disperse after colliding with a wall.
- It is unlikely that this is the result of a regime shift, and instead is indeed characteristic of solitons. Why this event occurs has not been investigated within this experiment. Basic soliton theory does not offer many answers, owing to the fact that this limit is where theory begins to break down.
	- Should I list out some possibilities for why it occurs?
- To expand on this investigation, one might attempt to create even larger solitons in shallow water, allowing a shallow water soliton to propagate for a very long time, or seeing what happens when one such soliton encounter a shore as opposed to a wall.

# Sources
Lab manual
- Most sources linked on the lab manual are dead links. I can still find them and cite them though.