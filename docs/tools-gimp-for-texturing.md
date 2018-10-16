# **Block Textures**
A very basic use of textures are the blockTiles, the textures for single blocks. They can be found in src/main/resources/assets/blockTiles or in the blockTiles subfolder of module's asset folder.

Block textures need to have the same name as the corresponding JSON block definition to be auto loaded.

At the moment the size of block textures is restricted to 16x16 pixels. They are stored as .png files and can contain transparency, e.g. for colored Glass.

Any textures that are no block tiles are located in src/main/resources/assets/textures or the corresponding mod directories. You can find several types of image files in there:

* Color gradients for grass or foliage
* GUI icons and backgrounds - elements assigned to the user interface, such as icons, inventory backgrounds, ...
* Skybox textures
* Effect textures such as breaking a block or the overlayed vignette
* Model textures such for the monkey heads > Note: Models and its textures/materials should be sourced out to modules.

# **Texturing: GIMP**
GIMP /ɡɪmp/ (GNU Image Manipulation Program) is a free and open-source raster graphics editor used for image retouching and editing, free-form drawing, resizing, cropping, photo-montages, converting between different image formats, and more specialized tasks.

GIMP is released under GPLv3+ licenses and is available for Linux, OS X, and Windows.

### **Website:** https://www.gimp.org
### **Github:** https://github.com/GNOME/gimp

## Uses of GIMP

GIMP is able to create different block textures that make up the in-game environment of Terasology, using various tools, such as gradients and texturing. 

### File Formats
* Import and Export: GIMP has import and export support for image formats such as BMP, JPEG, PNG, GIF and TIFF, along with the file formats of several other applications such as Autodesk flic animations, Corel PaintShop Pro images, and Adobe Photoshop documents. Other formats with read/write support include PostScript documents, X bitmap image, xwd, and Zsoft PCX. GIMP can also read and write path information from SVG files and read/write ICO Windows icon files.
* Import only: GIMP can import Adobe PDF documents and the raw image formats used by many digital cameras, but cannot save to these formats. An open source plug-in, UFRaw, adds full raw compatibility, and has been noted several times for being updated for new camera models quicker than Adobe's UFRaw support.
* Export only: GIMP can export to MNG layered image files (Linux version only) and HTML (as a table with colored cells), C source code files (as an array) and ASCII Art (using a plug-in to represent images with characters and punctuation making up images), though it cannot read these formats.

### Textures Creation
**Youtube Link:** https://www.youtube.com/watch?v=5AQshmlAyXY

### Using Gradient Brushes
![](https://www.gimp.org/tutorials/Tileable_Textures/grad_brush_dialog.png)

Gradient brushes can be accessed from the standard paintbrush dialog. 
1. “Use Color from Gradient” and start painting. 
2. You can also press the Gradient button to change the current gradient. 

### Examples of Brushes
1. “Grunge brushes” [can be found in the June 1999 edition of thegimp.com, in the brushes section.]

* Select one of those brushes
* Set the spacing to something reasonable (most default to 10 or so). I would suggest setting the spacing to about 80-120 or so. Of course, please experiment.
* Choose a gradient from the the gradient selector ( Dialogs -> Gradients).
* Add drawings on the image. If you want to stick to a very set pattern, your texture might look a bit more orderly.

![](https://www.gimp.org/tutorials/Tileable_Textures/grad_example_1.jpg)

### Making the Image Tillable
1. Offset your image by half its height, and half its width. Select  Layer -> Transform -> Offset. 
2. Choose the convient “x/2, y/2” option, and hit OK. 
3. Your image will now show what used to be at its edges at the center of the image. 
* The secret to making tileable images is to make this transition smooth.

![](https://www.gimp.org/tutorials/Tileable_Textures/grad_example_3.jpg)

For gradient painting with grunge brushes, this typicaly just means painting along those lines and try to avoid painting at the edges of the image when you do this. But if you do, just repeat the above steps again and you should be fine.

### Things to tweak
Of course changing the gradient type, and the brush will have a big effect on the look of the texture, but so will more subtle things like the opacity of the brush, and the paint mode can make for some interesting effects. These type of textures also seem to work well for layering two or three textures together with different layer modes.

All in all, this is nice and simple, and fast way to create some colorful textures.

![](https://www.gimp.org/tutorials/Tileable_Textures/texture1.jpg)
![](https://www.gimp.org/tutorials/Tileable_Textures/texture2.jpg)
![](https://www.gimp.org/tutorials/Tileable_Textures/texture3.jpg)
![](https://www.gimp.org/tutorials/Tileable_Textures/texture4.jpg)

## Sources
1. http://alternativeto.net/software/terasology/
2. https://github.com/GNOME/gimp
3. https://github.com/MovingBlocks/Terasology/wiki/Textures
4. https://en.wikipedia.org/wiki/GIMP#Features
5. https://www.gimp.org/tutorials/Tileable_Textures/
