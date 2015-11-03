bitmap.js reads a bitmap containing a color-palette, and a pixel array of any size. It creates a new bitmap file that shifts colors present in the original bitmap to another color already present in the original bitmap file. The color shift transform first creates a "colorsPresent" array containing a list of all palette index values that were referenced in the original bitmap pixel array. The transform loops through each pixel in the pixel array, looks up the index of the current palette reference value in colorsPresent, and then changes (shifts) the palette reference value of that pixel to the next value in the colorsPresent array. If the original palette reference was the last element of the colorsPresent array, the palette reference value is reset to the value at colorsPresent[0].


ORIGINAL ASSIGNMENT TEXT--

For this assignment you will be building a Bitmap reader and transformer.

It will read a Bitmap in from disk, run one or more color transforms on the bitmap and then write it out to a new file. This project will require the use of node buffers in order to manipulate binary data and your project should include tests, as well as a Gruntfile and package.json file. Also, make sure to run all your code through jshint and jscs.

The process will look something like this:


Open file using fs and read it into a buffer
Convert buffer into a Javascript Object
Run a transform on that Javascript Object.
Turn the transformed object back into a buffer.
Write that buffer to a new file.


You can also just directly manipulate the buffer.



The wikipedia article found here (Links to an external site.) describes the byte specification of a "windows bitmap file." We'll be working the simplest version, meaning no compression. Your project should be able to take a transform as a callback that will be run once the bitmap file has been read into a buffer. Your project should also include at least one transform.
