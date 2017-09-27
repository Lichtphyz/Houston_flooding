# Flood Water Detection 
### *with A Semi-Supervised U-Net*
<p align="center">
<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_Hm6IJy_low_res.gif" alt="Segmenting Floodwater - on an incomplete image footprint" width="600">
</p>

This repo contains a series of notebooks which made up the core steps of a 3-week project I recently conducted (and presented) at Metis SF in collaboration with DigitalGlobe.  You can find my [presentation slides here](https://docs.google.com/presentation/d/e/2PACX-1vQL4lvBRuwTnkPMcWgemC2gNoN51SNeYtfwQ4IiaP9jh20XWwRdVU7EMRi4_Et_-0ukVCt8l6Ogbp1K/pub?start=false&loop=false&delayms=3000) or you can read on for a more detailed description of the project.  It is also quite likely that I will be continuing to work on this project from time to time, so check back to see if I have added anything.

## Background:
This project was started as part of the [Metis/DigitalGlobe Data Challenge](http://deepcore.io/2017/06/06/Metis_Project.html) but when DigitalGlobe released a substanial dataset of the areas just hit by Hurricane Harvey (through it's [Open Data Program](https://www.digitalglobe.com/opendata)) the project quickly evolved into something more immediately relevent, but with data in less-pre-proceed state than the SpaceNet dataset I had been planning on working with.  

## Goal:  
A goal was set to built a model which (once trained) could quickly examine satillite imagry of an area, and create a 'mask' labeling each pixel as either flooded or not (and assign a likelihood of being flooded to each pixel).  This is an [image segmentation](https://en.wikipedia.org/wiki/Image_segmentation) problem.  Though it is unusal as both a before and after picture of the area will be fed to the model, to help label/segment the post-flood image.

Additionally, to be useful the model will really need to be able to predict over a wide area to be able to generate the type of large-scale flood extent maps which would be useful to disaster response or recover efforts.

IMAGE SEGMENTATION EXAMPLE PIC HERE

## Image Data
The post-storm satillite images I used for this project were primarily taken on October 31st, 2017 and can be found on DigitalGlobe's Open Data Program page for [Hurricane Harvey](https://www.digitalglobe.com/opendata/hurricane-harvey/post-event).  As time has progressed most images have been added to the website, so what is posted now is significantly more than what was available when I started, though the first images released were also amoung the best.  Each .geotiff file is 1.2 Gb in size, covers an area about 10x10km, are 20000x20000 pixels across in uncompressed 8-bit 3-color (Digital Globe internally used 8-color images, but those are rarely released to the public).

## Building a Training Set



## Baseline Model

As a baseline employed XGBoost to attempt to classify each pixel as flood water.  I gave it the same features I later gave to my U-Net model, but was forced to treat each pixel individually.  As such this model is not capable of using any information beyond the color of a pixel before and after the flooding occured.  As you can see it did moderately well at classifying one shade of floodwater, but misses most of the rest, and has quite a lot of rooftops, etc. labeled as flooding.

IMAGE HERE OF AUC CURVE AND PREDICTION

## U-Net Model

The project focused on building pixel-level labels for satelite imagery of the areas affected by Huricane Harvey, using them to train a Deep-Learinging Segmentation model (U-Net), and using the model to make predictions across large-scale image footprints.













I explain more about the important steps and workflow here:

*Note, the files currently posted are a portion of a work in progress, but are fairly representative of such.  I have not gone back and cleaned up my code at all, at least not yet* 

**Step 03** in particularly notable as it is a semi-supervised data labeling routine.  (Step 04 was removal of known water bodies from the training masks, but this was cut from the final product before completion, as it would be better (and easier) applied AFTER model prediction on an entire mosaic.  This feature has not yet been implimented, but could be if there was interest.)  Step 05b is a comparison with a 'baseline' XGBoost model.






### You can also see more on this project on my personal Blog, and likely soon on the DigitalGlobe Company Blog and possibly elsewhere!

Here's a couple of teaser images from the working model:

(this one is cool, because you can see the 'ghost of the past' in the areas with no post-hurricane imagery, but there was pre-hurricane imagery.  They are evidence that the U-Net model is not just using the post-hurriane images, but also takes the pre-hurricane condidtions into account.
<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_Hm6IJy_low_res.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_AtJBwz_3_3_1800.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_MHY2RT_1800.gif">
