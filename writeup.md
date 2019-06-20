# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[source]: ./examples/source.jpg "source"
[interest_region]: ./examples/interest_region.jpg 
[gray]: ./examples/gray.jpg 
[blur]: ./examples/blur.jpg 
[edge]: ./examples/edge.jpg 
[masked_edge]: ./examples/masked_edge.jpg 
[lines]: ./examples/lines.jpg 
[weighted]: ./examples/weighted.jpg 

---

### Reflection

### 1. Pipeline description

My pipeline consisted of next steps:

* Load image

![alt text][source]

* Define region_of_interest image

![alt text][interest_region]

* Convert source image to grayscale

![alt text][gray]

* Apply gaussian blur to a grayscale image

![alt text][blur]

* Apply canny edge detection to gaussian blur image

![alt text][edge]

* Mask canny edge detection and region_of_interest image

![alt text][masked_edge]

* Use hough_lines to find all the lines and draw a single left and right lanes

![alt text][lines]

* Weighted lane_detection and source images

![alt text][weighted]

### Procedure for extracting the lane ines

* Get the midpoint of all lines detected
* Determines whether the midpoint is loaded on the right or left side of the image and classifies it
* Use a simple linear regression to get m and b parameters the midpoint of left and right lines detected
* Define the x1, y1 and x2, y2 points to draw the left and right line to cover the region of interest    x = (y - b) / m 
* Draw the left and right lane lines

### 2. Potential shortcomings

One potential shortcoming would be what would happen when are shades in the road or too much light

### 3. Possible improvements to pipeline

A possible improvement would be to detect lane lines by color in order to have some redundancy
