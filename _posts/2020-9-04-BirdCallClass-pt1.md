---
layout: post
title: Identifying bird species by their calls with deep learning - Part 1, Dataset Construction
---

As promised in the last post, I'm getting back to talking about some data and the fun things one can do with it. While we already had some fun with the classifier I built for the many Chrises of Hollywood, that was just a little placeholder until I had time to prepare a more interesting\* dataset that I've been planning for a while!

I knew that the [inaturalist](https://www.inaturalist.org/observations) site has a large database of observations of living organisms from the whole world, including images, sound recordings and geolocation. The obvious choice would be to simply download lots of labeled photos of various species and train a classifier based on those, but I decided to go for the more fun challenge of trying to identify species of birds based on their sounds!\*\*

I vaguely remembered, from undergrad classes and talking to friends that research birds, that sounds can be represented by a type of plot called a spectrogram (see an example below) with time on the x-axis, frequency on the y-axis and intensity of the sound as a colour scale. And, since all the models I've worked with so far use image inputs, I figured I could simply use these kinds of plots as inputs to my model for now, rather than figuring out a way to input an actual sound into a neural network. \*\*\*

![Great Tit spectrogram]({{ site.baseurl }}/images/Parus_major_sonagram.jpg)
*Spectrogram representing the song of a Great Tit (Parus major), from Wikipedia (Maxime Metzmacher, CC BY-SA 3.0)

After some quick googling, I found instructions on how to make a spectrogram from a '.wav' file in python, using scipy, numpy and matplotlib. I copied and pasted a few lines of code into a notebook, with the changes needed to load my own file and got a pretty spectrogram... Yay!

![Raven spectrogram]({{ site.baseurl }}/images/raven-spectrogram.jpg)

That was easy enough, but then I started looking at the code I had used to make it, to try to understand what it had done to the input '.wav' to generate the image.

'''
samplingFrequency, signalData = wavfile.read("Raven.wav")
'''



## Footnotes
\* At least more interesting to me than looking at pictures of actors, but whatever floats your boat!

\*\* Technically, I should probably say "vocalisation", but I'll just stick with sound here because I'm not going to talk about other sounds made by birds that are not vocalisations, like wings flapping.
