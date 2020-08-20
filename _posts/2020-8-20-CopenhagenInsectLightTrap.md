---
layout: post
title: Quick exploration of a long-term insect collection dataset from Copenhagen
---

## Background

Earlier this week, I was scrolling through Kaggle to see what types of biology datasets were available there and ran across this one that seemed interesting: [Insect Light Trap](https://www.kaggle.com/University-of-Copenhagen/insect-light-trap), a huge 18-year insect collection effort done by the Zoological Museum of the University of Copenhagen, between 1992 and 2009. The work was [published back in 2015 and is open-access](https://besjournals.onlinelibrary.wiley.com/doi/full/10.1111/1365-2656.12452), with very detailed analyses on the diversity of groups found, correlating observations to time of year (big peak in summer, very few observations in winter, as I'd expect for northern Europe) and temperature/climate change. Do check out the paper if you'd like a deeper look into those aspects, because I'm just going to have a quick look at the dataset itself and see what kind of fun stuff I find in there.

## Getting the data

The first glance at Kaggle was great, it seemed like a nicely-formatted '.csv' with columns for various taxonomic levels, counts for each species, and collection start/end dates! Should make for a nice smooth start...

![Pandas read_csv FAIL!]({{ site.baseurl }}/images/InsectTrapPdReadError.png)

Or maybe not... that mention of 'utf-8' means there must be some weird character in the file that pandas is not happy with! To confirm that, I made a new '.csv' with just the first 5 lines of the full dataset and that loaded just fine, so the thing that's causing the problem is bound to be somewhere in the remaining 44,083 lines... yay! I'm trying to be smart in how I do these analyses, so that rules out scrolling down til I spot something weird.

I went back to Kaggle to redownload the file, holding onto the faint hope that something got messed up in the download. But no, redownloaded file produces the same error. I did notice that Kaggle has an option to export a dataset to Google Sheets, so I could use the GSuite option to export to '.csv' and hopefully that should generate a file that pandas is happy to read!

![Kaggle Gsheet export FAIL!]({{ site.baseurl }}/images/KaggleError.png)

After a good 30 seconds watching a spinny wheel that I hoped meant my data was being moved to the bowels of Google, I got an angry red exclamation mark and a useless error message! No, I'm not going to contact support, I'd rather scroll through the 40k+ lines than wait days and days for an answer.

I was about to start writing up the simple code to loop over the entire file and just build the dataframe myself, but then some lucky googling got me to a StackOverflow post where somebody mentioned trouble reading '.csv' with a similar character encoding error and that adding the flag ' encoding = "latin1"' to their '.read_csv()' call solved their issue! I had no idea whether that was the character set in my file (Atom just shows me "UTF-8" when I open it...) but I figured "Why not try?". Magically that worked, everything got loaded into a dataframe with no issues and I still have no clue what oddball character in the file was producing that error... some questions are best left unanswered!

## Exploring the data









## Footnotes

\* Get ready to deal with my inconsistent use of British and American words/spelling, cos it's all a mess in my head! I do try to stick to the British forms since it's what I used most recently, but I'm sure I'll miss a few here and there\*\*

\*\* Random footnotes are probably going to be frequent too... Side thoughts are a big part of my thought process and I always loved reading the wild footnotes in books like [The Mezzanine](https://en.wikipedia.org/wiki/The_Mezzanine) and [the whole Discworld series](https://en.wikipedia.org/wiki/Discworld).

\*\*\* By "collecting data into a '.csv', read that I took photos of the board when it got full and then typed everything up manually. I don't think even the best modern image recognition software could reliably decode my awful handwriting!"

\*\*\*\* Of course, the fallible human forgot to record when that switch happened!
