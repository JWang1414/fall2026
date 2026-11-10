I should have my lab notebook soon. So I'll just need this for today.

~9:00 arrival

Started off with a short conversation with JT (supervisor) and JZ (TA).
- The basis of this lab involves working with a high performance microscope, one where the thin lens equation does not apply
- We will be seeing regimes where objects cannot be resolved

Goal: For today, like always, my first goal is to familiarize myself with the lab, and learn how to use the equipment.

- I also spent some time setting up AHK, and porting some files over the lab computer. Note sure how relevant that is

10:47

I have been going through the provided "Course Lab Notes" to set some guidelines to go through the equipment. I intend to roughly follow it at the beginning, and deviate from it early into the lab (maybe day 1-2).
- This setup does not come with the CCS Compact Spectrometer. I have to get it from Larry. It will be useful later on if I choose to investigate a topic that has to do with colours and light (coloured LEDs, for example)

Quick sample calculation for the focus length of the lens I am using. The focal length is labelled to be 50 mm. I have an image in focus $6.65\pm 0.15$ cm from the lens. My camera is placed $23.3\pm 0.1$ from the lens.

The focal length from these rough measurements is:
$$
	\frac{1}{f} = \frac{1}{S_\text{image}} + \frac{1}{S_\text{obj}} \implies f = \left( \frac{1}{S_\text{image}} + \frac{1}{S_\text{obj}} \right)^{-1}
$$
$$
	\approx \left( \frac{1}{23.3} + \frac{1}{6.65} \right)^{-1} = 5.17345576
$$
Including the uncertainties, this is $5.17\pm0.09$.
- Something to note, the focal length on this lens is comparatively quite large for most of the microscopes we will be using in this lab. The ones that I have are 25 mm and 35 mm focal length. This one is 50 mm.

11:51

ThorCam Tools:

The horizontal and vertical line profiles show you the intensity across some horizontal or vertical line of the camera output. This is particularly useful for calibrating the camera exposure time, since it gives you an objective measurement to base your adjustments on.
- The lab notes claim that ~80% maximum intensity is where you want to be
- I have been using the auto-exposure option, and adjusting from there (I turn it on and off)

Other similar looks include the histogram (which shows you the distribution of intensities in the image) and "pixel peek" which shows you the values of the pixels your mouse is hovering over.
- The histogram can probably be used similarly to the line profiles
- I'm not sure what the pixel peek might be good for

Most other tools include annotations, image adjustments (like rotations). Nothing so interesting.

I have no idea what "Analysis Region of Interest" does. It seems to just put a square on the image I cannot remove.

Tricks for focusing the microscope:
- The camera and lens do not have a mechanism to make fine adjustments, but the sample does. This appears to be the only guaranteed way to make minute adjustments
- One can tighten or untighten the lens on its stand. This will move it forwards and backwards very slowly, but it also shakes the image quite a lot.