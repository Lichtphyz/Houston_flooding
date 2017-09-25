# Flood Water Detection 
## with A Semi-Supervised U-Net

The repo contains a series of notebooks which made up the core steps of a 3-week project I recently conducted (and [presented!](https://docs.google.com/presentation/d/e/2PACX-1vQL4lvBRuwTnkPMcWgemC2gNoN51SNeYtfwQ4IiaP9jh20XWwRdVU7EMRi4_Et_-0ukVCt8l6Ogbp1K/pub?start=false&loop=false&delayms=3000)) at Metis SF.

The project focused on building pixel-level labels for satelite imagery of the areas affected by Huricane Harvey, using them to train a Deep-Learinging Segmentation model (U-Net), and using the model to make predictions across large-scale image footprints.  Step 03 in particular is a semi-supervised data labeling routine.  Step 04 is missing because it was cut from the final product, and would better be applied AFTER predicted maps are made.

*Note, the files currently posted are a portion of a work in progress, but are fairly representative of such.  I have not gone back and cleaned up my code* 

You can also see more on this project on my personal Blog, and likely soon on the DigitalGlobe Company Blog and possibly elsewhere!

Here's a couple of teaser images from the working model:

<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_Hm6IJy_low_res.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_AtJBwz_3_3_1800.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_MHY2RT_1800.gif">
