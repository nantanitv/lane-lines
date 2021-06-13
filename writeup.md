# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidYellowLeft.jpg "Example Output Image"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted roughly of 6 steps.

#### 1. Convert the image to grayscale
#### 2. Apply the Gaussian Blur
#### 3. Apply the Canny Transform
#### 4. Mask the image with the region of interest
#### 5. Apply the Hough Transform
#### 6. Overlay the lines over the original image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first finding the average value of the slope of the lane lines on both left side and right side. Then, we find the points where the lines would end using said slope and the other ends of the lines. Finally, we can draw the lines using those coordinates!

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the lighting is strong and the road has concrete pavement. This would considerably reduce the contrast of color on the image and leads to mistaking other strong shadows in the region for lane lines. 

Another shortcoming could be if the lane lines are sharply curved. The pipeline would potentially struggle to find a straight line for each side since we only define straight lines to be drawn.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the known colors of different pavements as our guide to the color selection process. We can also apply this to the white and yellow lines on the road.

Another potential improvement could be to allow drawing curved lines, since we might encounter images where the car is going through sharp bends and the pipeline would fail to recognize the lane lines as they are not straight.

---

Nantanit V.

14 JUN 2021
