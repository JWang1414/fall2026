- Do not include an appendix
- 4-8 pages long. (Generally speaking) at most four figures and two tables
- Properly cite everything I do not own. Even in the draft
# Title
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
# Conclusions
- Brief overview of the major points
- Include main results. What are the major "take-aways"?
# Sources
Lab manual
- Most sources linked on the lab manual are dead links. I can still find them and cite them though.