# COMPUTER VISION NOTES - WEEK 2

- [Image Basics](#1-image-basics)
  - [Image generation](#i-image-generation)
  - [The HSV Colourspace](#ii-the-hsv-colourspace)
  - [Image Interpolation techniques](#iii-image-interpolation-techniques)
    - [Nearest neighbour method](#nearest-neighbour)
    - [Triangular Interpolation](#triangle-interpolation)
    - [Bilinear Interpolation](#bilinear-interpolation)
    - [Bicubic Interpolation](#bicubic-interpolation)
- [Convolutions](#2-convolutions)
  - [Resizing](#resizing)
  - [High Pass kernel](#high-pass-kernel)
    


### 3. Image Basics

- #### i. Image generation
  - An image is basically the projection of 3-D world into 2-D. 

  ![](https://i.imgur.com/OZxnkpt.png)


  - To capture the light information, we make use of the Bayer pattern over the CMOS (Complementary Metal-Oxide-Semiconductor) sensor, which lets in only a certain wavelength of light. This has twice the amount of green filters than other colours.

  ![](https://i.imgur.com/V0mASMU.png)

  ![](https://i.imgur.com/OH1jeKN.png)

  - Note: the amount of green light is more, as humans have more no. of green-sensitive rods than other colours, viz., blue and red

  - An image is just a matrix of light. Higher - 1, Lower - 0

  - Each individual element is called a Pixel
  - Coloured image -> 3-D Tensor in colorspace

- #### ii. The HSV colourspace 
  - Benefit of using other colorspaces is the different attributes we can modify as per our needs, e.g. changing the saturation or hue, by converting it into HSV
  - Hue: Color info
    Saturation: How prounounced the color is
    Value: General brightness (not grayscale, but looks like it)
    ![](https://i.imgur.com/kZ8O17Q.png)

  - Threshold saturating, hue shifting etc. are some possible operations

- #### iii. Image interpolation techniques
    - ###### Nearest neighbour: 
    ![](https://i.imgur.com/L1YOY1C.png)
    - ###### Triangle interpolation: 
    ![](https://i.imgur.com/NkHefry.png)
    - ###### Bilinear interpolation: 
     Find the closest pixels in a grid around the point of interest, basically linear interpolation of linear interpolations. Smoother than Nearest neighbour
    ![](https://i.imgur.com/TV8qgBO.png)
    - ###### Bicubic interpolation:
    ![](https://i.imgur.com/vw4tJ9D.png)
    
    ![](https://i.imgur.com/oD7Q0kF.jpg)
    
    ![](https://i.imgur.com/1l7JaCN.png) 
   
   The bilinear image, when zoomed in, has a starry look to it, which isn't noticebale in bicubic
    

### 4. Convolutions 
- Interpolation is useful in applications like resizing
- ##### Resizing 
    Steps:
    1. Match up coordinates
    2. Iterate over new pts.
        - Map to old coordinates
        - Interpolate old values
    3. Fill in the pixels
        - For outer pixels, padding is used
    ![](https://i.imgur.com/PTmD8ha.png)

- For reducing size, problem with resizing using interpolation methods is the fact that the closer pixels to the POI influence the image heavily, and therefore, can produce blocky artifacts
        ![](https://i.imgur.com/ZzLyubN.png)

- Alternatives to interpolation for reducing size:
    - Averaging: Basically summation of pixel values divided by no. of pixels in that square
    - This operation can also be called as a convolution. The matrix which slides over the image, containing the weights, is called the kernel.
    - Box filter (smoothing) then resized down, but still has some artifacts
    - For even smoothening, we can use Gaussian filters

- ###### High Pass kernel: 
  Finds edges, by diffrentiating pixels where the colours are similar
  ![](https://i.stack.imgur.com/Y5rkc.png)
  <br>
- Convolutional operations are the most important when it comes to image processing, when it comes to CNN
 

