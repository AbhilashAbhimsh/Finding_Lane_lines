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

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

1. Convert the image to gray scale
2. Blur the image using Gaussian Blur with kernel size 3
3. Apply canny Edge Detection algorithm to blurred image to get the edges in the image
4. Apply hough transform to the edge images to get the list of all lines
5. Out of all lines provided by the hough transform(i.e) points check if the points are inside the boundaries from the polygon vertices this will ive all the lines/points inside the boundaries for each side of lane lines to different lists containing  slope and intercepts of points
6. Take the mean slope and intercept for each side of line and draw only two lines on the images
6. Combine these line image and original image to get line on the original image

### 3. Suggest possible improvements to your pipeline
#### Shortcomings:
1. I have observe that the lane lines are not correctly filtered i.e. getting lane lines from another part of the image
2. I will be difficult to track the lane lines in the curve road

