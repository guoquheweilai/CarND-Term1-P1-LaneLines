# **Finding Lane Lines on the Road** 

## This writeup file is created from Writeup Template provided by Udacity.
## All rights reserved by Udacity

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


One potential shortcoming would be what would happen when there is no lines was detected in the image, my code will ignore that and draw no line.

Another shortcoming could be when the vehicle is entering a curve, my draw_line() will be mess up.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to perserve the last drawn line in the image when there is no line was drawn.
After a specific timeout (means no new line was drawn), it should raiseup a warning flag.

Another potential improvement could be to sorting the lines by region, using those lines in the near botton region which will be close to the vehicle. Then we can average the lines position then calculate the slope and offset. Finally we can get the correct lanes.

## Videos
Video recordings for success cases.  
Success to plot lane lines on solid white right video.  
![Success_Run_Part1](./test_videos_output/solidWhiteRight.gif)  
Success to plot lane lines on solid yellow left video.  
![Success_Run_Part2](./test_videos_output/solidYellowLeft.gif)  

End-of-File