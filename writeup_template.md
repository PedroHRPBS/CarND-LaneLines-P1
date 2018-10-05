# **Finding Lane Lines on the Road** 

## Writeup 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidYellowCurve_lanes_highlight.jpg "solidYellowCurve"
[image2]: ./test_images_output/whiteCarLaneSwitch_lanes_highlight.jpg "whiteCarLaneSwitch_lanes"
[image3]: ./test_images_output/solidWhiteCurve_lanes_highlight.jpg "solidWhiteCurve"
[image4]: ./test_images_output/solidYellowLeft_lanes_highlight.jpg "solidYellowLeft"
[image5]: ./test_images_output/solidWhiteRight_lanes_highlight.jpg "solidWhiteRight"
[image6]: ./test_images_output/solidYellowCurve2_lanes_highlight.jpg "solidYellowCurve2"

---

### Reflection

### 1. Pipeline description.

My pipeline consisted of 7 steps. 
* Convert image to grayscale
* Blur image using gaussian blur
* Use Canny algorithm to highlight edges on the image
* Define a region of interest on the image
* Transform series of dots into lines using Hough space
* Overlap image and lines
* Average and extrapolate series of lines to output only two lines

In order to draw a single line on the left and right lanes, I implemented the function
average_extrapolate_lines(). This function receives an image, a series of lines from
Hough algorithm, a y_min and a y_max.
First, we select only the lines that have a steep slope, and save the Xs, Ys and
Slopes of each one of them dividing between left and right lines (positive and negative
slopes).
With all values of X, Y and Slope, we calculate the average and determine a single line
for left and one for right.
After that, we extrapolate the lines to increase their length, to capture all the
length of the lanes.
Finally, I used draw_lines() to add the lines generated to the image.

Here there are the results obtained:

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
