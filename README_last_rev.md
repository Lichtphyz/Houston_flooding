# Flood Water Detection 
## with A Semi-Supervised U-Net

The repo contains a series of notebooks which made up the core steps of a 3-week project I recently conducted (and presented) at Metis SF in collaboration with DigitalGlobe.

You can find my [presentation slides here](https://docs.google.com/presentation/d/e/2PACX-1vQL4lvBRuwTnkPMcWgemC2gNoN51SNeYtfwQ4IiaP9jh20XWwRdVU7EMRi4_Et_-0ukVCt8l6Ogbp1K/pub?start=false&loop=false&delayms=3000)

The project focused on building pixel-level labels for satelite imagery of the areas affected by Huricane Harvey, using them to train a Deep-Learinging Segmentation model (U-Net), and using the model to make predictions across large-scale image footprints.

*Note, the files currently posted are a portion of a work in progress, but are fairly representative of such.  I have not gone back and cleaned up my code at all, at least not yet* 

**Step 03** in particularly notable as it is a semi-supervised data labeling routine.  (Step 04 was removal of known water bodies from the training masks, but this was cut from the final product before completion, as it would be better (and easier) applied AFTER model prediction on an entire mosaic.  This feature has not yet been implimented, but could be if there was interest.)  Step 05b is a comparison with a 'baseline' XGBoost model.


### You can also see more on this project on my personal Blog, and likely soon on the DigitalGlobe Company Blog and possibly elsewhere!

Here's a couple of teaser images from the working model:

(this one is cool, because you can see the 'ghost of the past' in the areas with no post-hurricane imagery, but there was pre-hurricane imagery.  They are evidence that the U-Net model is not just using the post-hurriane images, but also takes the pre-hurricane condidtions into account.
<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_Hm6IJy_low_res.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_AtJBwz_3_3_1800.gif">


<img src="https://github.com/Lichtphyz/Lichtphyz.github.io/blob/master/images/output_MHY2RT_1800.gif">
