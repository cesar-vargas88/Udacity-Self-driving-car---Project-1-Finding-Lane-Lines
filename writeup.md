# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

[source]: ./examples/grayscale.jpg "Grayscale"
[interest_region]: ./examples/grayscale.jpg "Grayscale"
[gray]: ./examples/grayscale.jpg "Grayscale"
[blur]: ./examples/grayscale.jpg "Grayscale"
[edges]: ./examples/grayscale.jpg "Grayscale"
[edge_mask]: ./examples/grayscale.jpg "Grayscale"
[lines]: ./examples/grayscale.jpg "Grayscale"
[weighted]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

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

![alt text][edges]

* Mask canny edge detection and region_of_interest image

![alt text][edge_mask]

* Use hough_lines to find all the lines and draw a single left and right lanes

![alt text][lines]

* Weighted lane_detection and source images

![alt text][weighted]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

* Get the midpoint of all lines detected
* Determines whether the midpoint is loaded on the right or left side of the image and classifies it
* Use a simple linear regression to get m and b parameters the midpoint of left and right lines detected
* Define the x1, y1 and x2, y2 points to draw the left and right line to cover the region of interest    x = (y - b) / m 
* Draw the left and right lane lines

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
