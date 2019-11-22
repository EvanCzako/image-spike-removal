# image-spike-removal
Rectifies pixel data spikes in images with adjustable threshold.

This code is intended to mitigate speckle noise, salt-and-pepper/impuse noise, and otherwise spikey data in images. Its intended application is image data that contains a scattering of pixels that have sharp intensity values differing significantly from those of their neighboring pixels. This type of noise is a common artifact of interferograms and radar images. Note that this function may not be an effective method of reducing other types of noise or image artifacts.

The code functions by identifying the nearest neighbors of each pixel and calculating the mean and standard deviation values of those neighbors. If the pixel of interest is further than a user-set threshold of standard deviations away from the mean value of its neighboring pixels, it will be considered a data spike. It will then be removed and replaced using the regionfill function of the Image Processing Toolbox.

NOTE: If you do not have the Image Processing Toolbox, you should replace the call to the regionfill function in this code with a call to my fill_region function (included in this folder), which accomplishes the same task with comparable computational efficiency. Either will run reasonably quickly, even for higher-resolution images.

Please read function descriptions for full instructions on their use. Please see examples embedded in function descriptions for demonstrations of use.
