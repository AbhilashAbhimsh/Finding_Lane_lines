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
The Steps to I followed as follows:
1. Convert the image to binary image
2. Blur the image to take out the noise from the pixels
3. Apply Canny edge detection onto to blurred image to get images with only edges
4. Apply the Region of Interest[Polygon] on the edge images to get only the edges in the region
5. Apply Hough transform and get the list of lines in the images[most likely the Lane lines]
6. Get the slope of lines one for each lane lines and divide it as left slope and right slope using the condition as slope greaer than 0 as right slope and slope less than zero left slope
7. Take the measn of each slopes and draw 2 lines one for right lane and one for left lane
8. combine the 2 lane line image with actual real image to get the lane lines drawn onto the image

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline
1. If there is any small lines in the picture between 2 lane lines they are also taken for approximation[Seen in the second video] need to find a way to avoid that
2. As we are taking only lines approximation we wont be able to do that for curved roads


### 3. Suggest possible improvements to your pipeline

We can store the mean of the last frame and update the current frame by taking the mean between last frame mean slope and intercept and this frame current slope and intercept
