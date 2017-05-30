# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
- Convert to greyscale
- Apply Gaussian Blur
- Apply Canny Edge Detection
- Apply Region Mask
- Apply Hough Lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

- Dividing the hough lines into left and right based on slope
- Then these line points are used calculated an average line, y=mx+b for left and right
- Then using this find x1 and x2 points to draw on the image, since y1 and y2 are constants

### 2. Identify potential shortcomings with your current pipeline

- Updated draw lines function is great for linear lines but for curves, there are issues.
- I am not sure of the current performance of this pipeline and how it matches to other solutions
- There needs to be enough lane line points
- Dark images were not tested for
- Walls that are the lane lines was not tested for
- No fallback for a worst case scenario(no lane lines)
- Image is assumed to be undistorted
- This pipeline isn't providing the upcoming lane info for steering curves

### 3. Suggest possible improvements to your pipeline

- I have some hardcoded constants that need updating
- Redesign draw lines for curves, or lower line length
- Pipeline is hardcoded to only get the closest lane lines. To get outer lane lanes, would require a redesign
