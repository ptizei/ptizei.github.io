---
layout: post
title: First look at the data from my garden compost pile (AKA, how simple data can be misleading!)
---

As the first real post in this blog, we're going to look at the longest-running personal project that I have right now: the compost pile that I started in the garden about 4 months ago to try to improve the fertility of the soil.

I had tried growing some courgettes/zucchinis\* in the garden and they kept drying out or dying of apparent fungal infections. Then I started following the tweets from a gardener in the US ([@BuildSoil](https://twitter.com/BuildSoil)) who talks a lot about composting as a way to improve soil quality and prevent a lot of these problems, so figured I could give it a try!

Since around April, every food scrap that is not meat or prepared food (fruit/veggie peels, egg shells, stalks, etc) has been going into piles like in the photo below, along with lawn clippings and dry leaves.

COMPOST PILE PHOTO!!!!

Then, I just make sure to keep the pile moist and turn it 1-2 times a week. Every month or so, I split the pile, move the new half elsewhere, and then just add new scraps into the new pile. After another couple of weeks, the old pile is ready to be used as soil for planting. The new plants are still not perfect, but they certainly look better than they did before I started this whole process!

All that was just to introduce the actual topic of the post, which is the data I started collecting in late June by weighing the scrap inputs that went to the compost pile. My initial reason to collect this data was to try to later produce some estimate of the amount of carbon that I'm putting back into the soil. But, not long after starting to record the data, I started thinking whether there were any interesting patterns that I could pick out from this data, like whether it would be possible to detect days that I prepare more complex meals by higher amounts veggie peels going into the pile on those days.

So I set up a very elaborate data recording system: a whiteboard stuck to a wall, to write the amount of material going in each day! I also wrote next to each entry whether I cooked a meal that day or not, a simple boolean variable that maybe I could use to train some sort of classifier from the weight data labeled with those 1s and 0s??

DATA BOARD!!!

If you can decipher some of my hieroglyphs, you'll see that some days don't have recorded entries. Was no food scrap produced at all on those days? Maybe that did happen on a few days, but certainly not all of them! What happened on most of the days with no entries is that I was either too busy to bother taking out the scraps that day and just added it to the amount for the next day, or I wasn't at home at all. So that's already one confounding factor to keep in mind when we start looking at the actual data!

Which is exactly what we're going to start doing! I collected about 1.5 months of data into a '.csv'\*\*\* and loaded it into a Jupyter notebook([uploaded here if you'd like to have a look at the inside of the sausage factory](LINK TO NOTEBOOK!!!!)) to make some plots.

LINEPLOT WITH NO SLIDING AVERAGE

pretty noisy, maybe a sliding average will help clean it up a bit?

LINEPLOTS WITH SLIDING average

better!

increasing trend? Probably another artifact caused by humans! From day 0, I was collecting the scraps in a small-ish bowl, which meant  that some days I had to make more than one (extremely inconvenient, 30-second) trip out of the kitchen and into the garden. Also, whenever the bowl was full, it was very tempting to avoid the additional trip to the compost tile by just throwing a few tiny, insignificant bits of scrap into the normal rubbish bin. Around day 15 \*\*\*\* I switched the bowl for a larger container that can easily hold the total scrap for 2 days, allowing for a more convenient composting schedule.



Now that I see the data, I guess the bits that sometimes went to normal rubbish weren't so insignificant... If we just look at the sliding average past day 15 or so, the trendline there would probably be parallel to the x-axis. I'll just keep it as an eyeballed trend for now and save this additional analysis for a future revisit of this ongoing dataset. This post is already **way** longer than I envisioned it!

 some compostable bits into the normal rubbish and avoid an additional trip to the compost tile. So,

TABLE WITH MEANS ON COOK AND NO COOK days

cooking -> more compost? Probably not, let's see the actual no cook DATA

SCATTER plots

poorly defined states for this variable made it meaningless!

What can we conclude from all this? 1) can't just blindly trust any type of automated analyses on a dataset without exploring it a bit and understanding how it was generated. If I simply received this dataset with no explanation for the 0 compost input days, I could interpret that as a much bigger variability in the amount of scraps produced every day than is visible in the sliding window plots.

2) Humans are fallible/lazy! Of course, I wrote that last statement in the third person to sidestep some of the guilt there, but the point remains that an inconvenient/labour intensive data collection process is error-prone and that will have implications on the quality of the dataset!

3) poorly defined categories lead to useless data! More time spent planning would have led me to either define this in a way that is more internally consistent or simply made me realise that I couldn't make that distinction, which meant I didn't need to bother recording that information at all!


\* Get ready to deal with my inconsistent use of British and American words/spelling, cos it's all a mess in my head! I do try to stick to the British forms since it's what I used most recently, but I'm sure I'll miss a few here and there\*\*

\*\* Random footnotes are probably going to be frequent too... Side thoughts are a big part of my thought process and I always loved reading the wild footnotes in books like The Mezzanine and the whole Discworld series.

\*\*\* By "collecting data into a '.csv', read that I took photos of the board when it got full and then typed everything up manually. I don't think even the best modern image recognition software could reliably decode my awful handwriting!"

\*\*\*\* Of course, the fallible human forgot to record when that switch happened!
