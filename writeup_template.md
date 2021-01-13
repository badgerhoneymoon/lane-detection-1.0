# **Finding Lane Lines on the Road** 

## Writeup Template

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/grey.jpg "Grayscale"
[image2]: ./test_images_output/edges.jpg "Edge detection"
[image3]: ./test_images_output/masked_edges.jpg "Edges after masking"
[image4]: ./test_images_output/lines.jpg "Left & Right lines"
[image5]: ./test_images_output/result.jpg "Result"
[image6]: ./test_images_output/hough_lines.jpg "Hough lines"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 
1. I converted the images to grayscale:

![alt text][image1]

2. Canny filter edge detection is implied:

![alt text][image2]

3. Put a quadrilateral mask on the region of interest

![alt text][image3]

4. Then I used Hough transformation to detect lines:

![alt text][image6]

5. In order to draw a single line on the left and right lanes, I modified the draw_lines() function by averaging centers and slopes of lines detected after Hough Transformation:

![alt text][image4]

6. Merging lines and our original image gives us this: 

![alt text][image5]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
