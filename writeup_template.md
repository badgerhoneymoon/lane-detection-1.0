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
**1. I converted the images to grayscale:**

![alt text][image1]

**2. Canny filter edge detection is implied:

![alt text][image2]

**3. Put a quadrilateral mask on the region of interest

![alt text][image3]

**4. Then I used Hough transformation to detect lines:

![alt text][image6]

**5. In order to draw a single line on the left and right lanes, I modified the draw_lines() function by averaging centers and slopes of lines detected after Hough Transformation:

![alt text][image4]

**6. Merging lines and our original image gives us this: 

![alt text][image5]


### 2. Identify potential shortcomings with your current pipeline


* One potential shortcoming would be what would happen when we have curvatures on the road. Line approximation would be irrelevant and we need to dynamically change lenghts of our drawn lines. Now they are hard-coded.

* Another shortcoming could be night time with low visibility. Our filter parameters are adjusted to daytime.

* Another shortcoming could be when a car in front of us blocks the sight of lanes. Without prediction model we would fail to recognize.



### 3. Suggest possible improvements to your pipeline

* A possible improvement would be to use other approximations when we have twisting road

* Another potential improvement could be to use historical data to smooth or even predict the lane lines

* To tackle nighttime we would need to determine which part of the day we witness and depending on that use different filter parameters.


