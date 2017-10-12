# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/output_solidWhiteCurve.jpg "solidWhiteCurve"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps.
1. Converted the images to grayscale.
2. Applied the gaussian noise kernel.
3. Applied Canny transform
4. Applied an image mask
5. Applied hough lines transform
6. Draw transparent lines on the image
7. (Optional) Save image to the subdirectory "test_images_output" with prefix "output_"

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by seperating the lines by slope, removing horizontal and vertical lines and averaging the lines then getiing the slope and offset. Finally, I extrapolated the lines to the botton of the image and the top of the lane.

Below it is one of my output images.
You can find more under the subdirectory "test_images_output"

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
