# MultiMedia2: Color Representation & Spaces
This program will enforce a practical understanding of color representations, color spaces and data structures normally used in color analysis. 

The program will take a few parameters.
• InputImage.rgb – This is the input image that contains a one of more of colorful
objects some of which (or none of which) will be in your library.
• A list of objects object1.rgb object2.rgb ...objectn.rgb which will represent your
library of objects.
All the images will be of the same size 640x480.


Process and Execution:
The main data structure is a color histogram. A histogram is a
representation of the distribution of data and the frequency of each type of data. Given a gray scale single channel image, its associated histogram is
illustrated by the example below, where the X axis describes all possible values of a pixel
0-255 and the Y axis gives the number of times the pixel value occurs in the image.

A color representation has three channels R, G and B. Y
1. Creating histograms for object images.
The input parameters to the program has a list of objects (from a library). All these object
images are given against a constant green chroma background. The green chroma
background is given so you can conveniently choose pixels that belong to the object. Create
multiple histograms for each object image given on the command line list.
2. Creating a histogram of the input image
Given the input image, assuming that it contains object(s). Create a histogram of the
image. Making not of the fact that the position/orientation/scale of
an object in the input image will be very different from its proportions in the object image.
This will result in the number of pixels that represent the object in the two images be vastly
different, though there is a pattern to the distribution which will be similar in both
histograms.
3. Object detection using histogram matching
Given object histograms and the input image histogram, detect the presence of an object histogram in the input image histogram
by comparing all the channels. Given that color is the main purpose of comparison, implement this matching algorithm in a space that ignores luminance eg
• Convent the image from RGB to HSV, and create histograms for H.
Ignore S & V and compare the H (hue) histogram between the input
image and library image objects.
  - color conversion: https://en.wikipedia.org/wiki/HSL_and_HSV & https://www.cs.rit.edu/~ncs/color/
5. Object Localization
Once the object is detected, highlight the pixels in the image that correspond to the object either by highlighting them
or showing a bounding box around them. To achieve this, keep track of [x,y]
locations of pixels when forming the histogram.



How to run this program:

run from the command file, first compile:

>> javac ImageDisplay.java

and then run the program with desired inputs, for example:

>> java ImageDisplay data_sample_rgb/Apple_image.rgb data_sample_rgb/Apple_object.rgb

the first command line argument is the input image and the seconnd red of then command 
line argemnts are the obejct/objects that need to be detected within the input image

/////

the python script is used for visualization, parts of the program arte commneted out and those 
commented out sections were used for testing such as coliing the pixels, 
saving the historgam datya to a CSV file, and reading the CSV data and displaying the histograms using python 
