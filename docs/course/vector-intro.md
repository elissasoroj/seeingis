
# What is a Vector Image?

## Vector vs. Raster Images
It is difficult to explain the fundamental differences between vector and raster images without discussing how images are displayed and reproduced. The short answer is that raster images are made of pixels, whereas vector images are specified by mathematical descriptions of each element in the image. Practically, this means that a vector image can be scaled up and down without loss of resolution, whereas a raster image will become blurry if it is scaled larger than its original size. 

It is worth taking the time to understand resolution and scaling, which otherwise becomes a frustrating black box - especially when dealing with journal submissions. 

## Image Display
Images have to be displayed somewhere, be it a printed page, a screen, or projected on a wall. The way that images are produced may be different than how they are **re**produced, which can introduce confusion when dealing with files. For example, a vector image may be created within a vector software on a computer (where it will be displayed on a screen). The vector image may then be displayed on a webpage *in its original vector form*. However, it may also be converted into a **raster** image, which is a necessary step before it can be printed or uploaded to certain websites, such as social media. 

This page covers the basics of dealing with vector and raster images, and some considerations to keep in mind when creating your own images. 

### Pixels, Resolution, and File Sizes
The term **pixel** does not actually have a specific definition - it can refer abstractly to the smallest unit an image, but it turns out this isn't a very practical definition because that unit is highly context-dependent.

#### Resolution
Resolution is another term that lacks specificity. Resolution is often defined in terms of pixels, which is where the ambiguity arises. From a practical standpoint, resolution refers to the **dimensions in pixel units of an image.** 

Despite the ambiguity, this is the most useful way to think about the "size" of an image. The pixel dimensions tell you everything you need to know about reproducing that image, which will change depending on the context (i.e. if you are reproducing the image on a screen, or in print). The thing that people find most confusing is that pixels don't have set corresponding physical units - so it is hard at first to conceptualize what it means to define an image in this way. I have found it useful to think about images in terms of how much **information**, or literal **data**, it has. For raster images, the more data it has (i.e. the higher the resolution), the bigger it can be (successfully) reproduced on screens and in print. As we will get to at the end of this page, the power of vector graphics is that, unlike raster images, they are not defined using pixels. This means that the amount of information they contain does *not* constrain what size they can be displayed at. In other words, vector images **do not have a resolution**. 

#### Screens
Screens are made up of physical, hardware pixels - the tiniest unit of light that makes up the screen. You can think of your screen as a grid of tiny light bulbs, each of which can be controlled individually. The brightness of each pixel can be adjusted to form a black and white picture - but color is slightly more complicated. Each "pixel" needs to be subdivided into 3 sub-pixels of a different color: red, green, and blue. Red, green, and blue light at their brightest combine to form white light. The brightness of each sub-pixel can be adjusted to form other colors, and pixels that are off will appear black. 

We can use this idea to start thinking about file sizes and resolution. In the same way you screen can display an image by adjusting the amount of red, green, and blue light emitted by each pixel, an image file can be stored as a grid of data (pixels) that specifies a color for each cell. There are different ways that color value can be stored. Color can be encoded in a way that corresponds directly to screen hardware, in other words, by a value corresponding to the amount of red, green, and blue that should be mixed to produce the color. That means for each pixel in your image, you need to store 3 values, each of which can take on a value of 0-255. For example:
* (255, 255, 255) is highest values for all three colors, which produces white
* (0, 0, 0) is no color in color in RGB, or black
* (255, 0, 0) is pure red

...and so on. If you have spent time designing websites or generating images using code (e.g. R, Python) then you have likely encountered HEX codes. HEX, or hexadecimal numbers, are 6-digit codes that correspond to specific RGB values. They reduce the number of bits needed to encode color information and are easier to deal with than RGB values. 

However, there are other ways of encoding color information. CMYK specifies four values (corresponding to cyan, magenta, yellow, and black), which is also how colored inks are mixed for printing, as discussed below. 

Changing the color profile of a file from RGB to CMYK will change the file size. This may seem counter-intuitive, but this is because *more* information needs to be stored when a color is specified in CMYK than if it is specified in RGB. 

#### Print
Printed images are also made up of pixels, but they are printed pixels - often referred to as dots. Printers generally use a mixture of Cyan, Magenta, Yellow, and Black (CMYK) inks to achieve color. The printing area is divided into a grid of dots, and a dot of each ink color needs to be placed at each position. The radius of the dot is adjusted by the printer in order to achieve the illusion of those colors mixing. 