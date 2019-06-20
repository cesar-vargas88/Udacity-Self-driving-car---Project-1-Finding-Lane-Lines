# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

To complete the project, two files will be submitted: a file containing project code and a file containing a brief write up explaining your solution. We have included template files to be used both for the [code](https://github.com/udacity/CarND-LaneLines-P1/blob/master/P1.ipynb) and the [writeup](https://github.com/udacity/CarND-LaneLines-P1/blob/master/writeup_template.md).The code file is called P1.ipynb and the writeup template is writeup_template.md 

To meet specifications in the project, take a look at the requirements in the [project rubric](https://review.udacity.com/#!/rubrics/322/view)

# **Finding Lane Lines on the Road** 

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

The Project
---

## If you have already installed the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) you should be good to go!   If not, you should install the starter kit to get started on this project. ##

**Step 1:** Set up the [CarND Term1 Starter Kit](https://classroom.udacity.com/nanodegrees/nd013/parts/fbf77062-5703-404e-b60c-95b78b2f3f9e/modules/83ec35ee-1e02-48a5-bdb7-d244bd47c2dc/lessons/8c82408b-a217-4d09-b81d-1bda4c6380ef/concepts/4f1870e0-3849-43e4-b670-12e6f2d4b7a7) if you haven't already.

**Step 2:** Open the code in a Jupyter Notebook

You will complete the project code in a Jupyter notebook.  If you are unfamiliar with Jupyter Notebooks, check out [Udacity's free course on Anaconda and Jupyter Notebooks](https://classroom.udacity.com/courses/ud1111) to get started.

Jupyter is an Ipython notebook where you can run blocks of code and see results interactively.  All the code for this project is contained in a Jupyter notebook. To start Jupyter in your browser, use terminal to navigate to your project directory and then run the following command at the terminal prompt (be sure you've activated your Python 3 carnd-term1 environment as described in the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) installation instructions!):

`> jupyter notebook`

A browser window will appear showing the contents of the current directory.  Click on the file called "P1.ipynb".  Another browser window will appear displaying the notebook.  Follow the instructions in the notebook to complete the project.  

**Step 3:** Complete the project and submit both the Ipython notebook and the project writeup
