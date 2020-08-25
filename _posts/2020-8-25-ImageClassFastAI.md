---
layout: post
title: Image classification with FastAI
---

Last weekend I started doing the [Practical Deep Learning for Coders](https://course.fast.ai/) online course from the creator of the fastai python library, [Jeremy Howard](https://twitter.com/jeremyphoward). I'd been wanting to start it for a few weeks but I saw a tweet by Jeremy saying that new versions of the library and the course would be released, and now that they are out I think it was worth the wait! I had seen the first lecture of the previous version of the course and even started the fun process of setting up a google compute account to run the code from the course using their free credits on signup, as the course recommended until then. But now for this version, they simplified and just recommend using the free options in Google Colab or Paperspace, which has been super easy to set up!

The course itself seems like it will be a very practical introduction to various applications of deep learning, while also going down into some detail on what the models are actually doing and how to use the many features contained inside fastai, while just requiring some knowledge of python. In the very first lesson, you get to train an image recognition model to reliably classify photos of cats vs dogs, using a dataset supplied by the course and with just a few lines of code that took less than a minute to run. But it really starts getting fun in the second lesson, where they start the process from the stage where the dataset gets built and take it all the way to training the model, checking its performance, and deploying it to a web application for prediction!

The example they give in the lecture is to build a dataset of images of different types of bears (black, grizzly, and teddy!) by downloading images via Bing Image searches\*. After a bit of pain actually getting permission on my Microsoft account to use the image search API, it went pretty smoothly with just a few commands to download the images into separate folders for each class, get rid of anything with errors, assign labels, split train/validation sets, and actually train the model!

![Bear dataset training]({{ site.baseurl }}/images/Bears.png)

The table above tells me that from the first stage of training, the model was already getting 100% accuracy (0.0 error rate) on the 20% of the data set aside for validation. After 4 more epochs (rounds) of fine tuning the model, it actually got a little bit worse, but it was still an error rate of just over 1% which is great. The problem with having a near-perfect model straight from the beginning is that it doesn't leave much room for improvement, which is when you actually get to learn something new! And looking at a random sample of the images in the dataset (below), there's some pretty obvious differences between teddy bears and the others, but even black and grizzly bears differ enough in fur colour that it's super easy for us lowly humans to pick them out immediately.



## My own dataset

Jeremy promises right at the beginning that it should be easy to get near state-of-the-art performance pretty easily with transfer learning in fastai and I know that the best models can now achieve superhuman performance, so I decided to make a dataset that **I** couldn't classify reliably as a more fun challenge! While racking my brain for classes of images that would be easy to download by searching and were also hard to tell apart, I remembered some twitter memes about Hollywood actors named Chris that all look alike, but I couldn't remember all their last names... so I turned to google's ML models for help with the query "actors named chris that look similar". 

That gave me one of those suggested result boxes with the title "Who are the 5 chrises": Evans, Hemsworth, Pratt, Pine, and Rock. I don't quite agree that Chris Rock looks very similar to the other ones there, but I guess that must be a case of text processing models like OpenAI's famous GPT-3 outputting wrong results that look just fine at a first glance! I decided to keep Rock in as a sort of internal control that I would be able to recognise, along with Pratt who I think I can regognise better from seeing him a lot in *Parks and Recreation* and *Guardians of the Galaxy*.

So I did a Bing query for each of the Chrises, which gave me about 150 images of each, with a few samples below. As I expected, I can recognise Pratt and Rock, the others are all the same person to my eyes that are pretty bad at facial recognition! I also spotted a black-and-white image in the set, which I've read can be a problem if there are not too many BW examples in the dataset, so I'll keep an eye out for that after the model is trained.

![Chrises]({{ site.baseurl }}/images/Chrises.png)








## Exploring the data



## Footnotes
\* This is certainly the first time I've ever actually used Bing for anything and apparently Bing Image search is the best way to get decent number of images by a search through an API!
