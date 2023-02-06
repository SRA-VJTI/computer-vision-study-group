# COMPUTER VISION NOTES - WEEK 1

- [INTRODUCTION - Tiers of CV](#1-introduction---tiers-of-cv)
    - [Low - level](#i-low---level)
    - [Mid - level](#ii-mid-level-vision)
    - [High - level](#iii-high-level-vision)
- [Human Vison](#2-human-vision)
    - [Evolution of eyes](#i-evolution-of-eyes)
    - [How human eyes work?](#ii-how-human-eyes-work)
    - [Light](#iii-light)
    - [For computers](#iv-for-computers)

## 1. INTRODUCTION - Tiers of CV

### i. Low - level

Operate on pixel values of the images
Examples:
- Resizing of an image.   
![](https://i.imgur.com/UC2FA1p.png)

- Also covers all image adjustments, like grayscaling, exposure level, saturation, hue (color correction), etc..
    - Exposure: Exposure is the amount of light that reaches your camera's sensor, creating visual data over a period of time.
    - Hue: Hue is the wavelength within the visible-light spectrum at which the energy output from a source is greatest.Hue represents the color being displayed, as found on a red-green-blue scale, color wheel or grayscale. The intensity of the primary colors or gray displayed grows with increased brightness, but the color itself does not change.
    - Saturation: In photography, the term 'saturation' describes the depth or intensity of colour present within an image. Saturation is also referred to as 'chroma'; The more saturated an image is the more colourful and vibrant it will appear, less colour saturation will make an image appear subdued or muted.  
![](https://i.imgur.com/6ho7B9X.png)

- Feature extraction
  - Edge detection: Edge detection is an image processing technique for finding the boundaries of objects within images.  
  ![](https://i.imgur.com/H3pFXqD.png)

  - Oriented gradients: The different colors here represnt different features in the image.  
  ![](https://i.imgur.com/onyJ5cx.png)


  - Segmentation: grouping pixels based on a range of colors  
![](https://i.imgur.com/X7Ahmav.png)

### ii. Mid-level vision

- Image to Image mapping
  - Panaroma stitching  
  ![](https://i.imgur.com/O24ioLd.png)
- Image to World maping
  - Multi view stereo (Parallax effect): Stereoscopic Imaging is a technique used for creating or enhancing the illusion that an image has depth by showing two slightly offset images separately to each eye of the viewer. Both images are of the same scene or object but from a slightly different angle or perspective.  
  ![](https://i.imgur.com/gVhH0Rm.gif)

  - Structured light scan (3D depth mapping): The light source from the scan head projects a series of parallel black and white patterns onto the scan target. When light projects onto the object's surface, the patterns become distorted. The cameras capture these images and send them to the 3D scanning software for processing.  
      ![](https://i.imgur.com/ASttWTQ.png)

  - Range finding (LIDAR): Range imaging is the name for a collection of techniques that are used to produce a 2D image showing the distance to points in a scene from a specific point, normally associated with some type of sensor device, like LIDAR (Light Detection and Ranging)  
  ![](https://i.imgur.com/op65sdc.jpg)

  - Optical flow: Tracking of Movement of a group of pixels in videos  
  ![](https://i.imgur.com/sCkDRT4.gif)

  - Time lapses, from images  
  ![](https://i.imgur.com/4PYYxaI.gif)


  
### iii. High-level vision
Extracting semantics (meaning) from the images
Involves Convolutional neural networks
- Classification (what is in the image?)
- Image tagging (Things in the image)
- Object detection (Objects and where are they)
- Semantic segmentation (Labelling pixel values to a certain part of an image)
- Instance (= Detection + semantic segmentation)  
![](https://i.imgur.com/ocV32sk.png)
- Semantic to images also possible

## 2. HUMAN VISION
Eyes; sensors for vision

### i. Evolution of eyes
![](https://i.imgur.com/opci96r.png)

The more complex the eyes get, the more acuity is obtained, i.e, the direction from where the light is coming.
Refractive elements help in letting in more light and also increases acuity
Focusing is also possible by changing the refraction of the lens

![](https://i.imgur.com/paG0LMF.png)

Hence, all these attributes of a complex eyes allow for image formation.

### ii. How human eyes work?
The light entering firsts hits the retina, which is then absorbed by the photosensitive cells (rods and cones). This info is then transmitted through the optic nerve to the visual cortex

- Rods: for low light, monochrome vision. 
- Cones: Colored, detailed vision

![](https://i.imgur.com/IltCyt6.png)

- Fovea: small area on the retina, has highest visual acuity

![](https://i.imgur.com/qU7rrnu.png)

- ![](https://i.imgur.com/0hcWA7b.png)

- Brains and Eyes co-exist
  Visual Cortex interprets data as follows
  - V1: primary vc, edge detection and spatially sensitive
  - V2: secondary vc, Helps with size, shapes, sends signals to v3-v5 and feednack to v1  
![](https://i.imgur.com/OxJU46x.png)
    A lot of processing in brain (almost 2/3rd) is dedicated to vision.
    
- 3D Interpretation  
![](https://i.imgur.com/dlWgJjf.png)
    - Eye uses blinking to reset the rotational axis
    - Visual cortex makes high level decisions

### iii. Light

- A EM wave, having both particle and wave nature.
- Visible: 400 - 700 nm
- Color of an object is dependent on the incident light and and object's reflectance.
- Photoreceptors are more responsive to certain wavelength.  
- ![](https://i.imgur.com/HRwO327.png)
- We can percieve blue color less, as we have less cones responsive to that color.
- Any color can be represented as a combination of different wavelengths, and follows linearity.

- A colorspace is formed when a set (min 3) of primary colors are taken  
 ![](https://i.imgur.com/EPeMLYm.png)  
 ![](https://i.imgur.com/UOst68a.png)
 The above image was famous in 2020 for basically crashing android phones, especially Samsung phones, wherein if this image was set as the phone's wallpaper, the device was in a bootloop. The reason here was the fact that the photo was taken in ProPhoto RGB format, and while converting it into sRGB, Android rounded up the final pixel value to 256, which was beyond the 255 limit initially set, so it caused a looping error, which wouldn't be fixed, as there was no precaution against it.

 
### iv. For Computers
  - Image is represented as grid of pixels
  - Each pixel has 3 channels, called RGB
  - But RGB is not accurate and can't represent every color seen in the real world.
  - sRGB is not linear, but actually gamma-compressed. Basically, light tones are compressed, and dark tones are expanded
  - So, colors can be represented using numbers
  - Grayscaling - approximated from RGB by taking a weighted sum, which involves gamma decompressing, calculating lightness and gamma compressing.
  - RGB representation   
  ![](https://i.imgur.com/rfTKMfe.png)
  - HSV representation  
  ![](https://i.imgur.com/9kxNnrN.png)




    


