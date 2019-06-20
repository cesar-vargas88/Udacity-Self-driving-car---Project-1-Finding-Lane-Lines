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
[./examples/gray.jpg]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of next steps:

Define region_of_interest image
Convert source image to grayscale
Apply gaussian blur to a grayscale image
Apply canny edge detection to gaussian blur image
Mask canny edge detection and region_of_interest image
Use hough_lines to find all the lines and draw a single left and right lanes
Weighted lane_detection and source images

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

Get the midpoint of all lines detected
Determines whether the midpoint is loaded on the right or left side of the image and classifies it
Use a simple linear regression to get m and b parameters the midpoint of left and right lines detected
Define the x1, y1 and x2, y2 points to draw the left and right line to cover the region of interest    x = (y - b) / m 
Draw the left and right lane lines

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
