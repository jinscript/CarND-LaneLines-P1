# **Finding Lane Lines on the Road** 

### 1. Pipeline Description

My pipeline consisted of following steps. 
* Gray Scale: convert image in to gray scale.
* Gaussian Blur: apply Gaussian Blur to smooth gray scaled image.
* Canny Edge Detection: apply Canny Edge detection to generate edges.
* Mask: apply a mask to only keep edges inside bottom trapezoid.
* Hough Transform: generate lines from edges.
* Draw lines:
.Following steps are taken for generating one line for left lane and one line for right lane.
Taking line for left lane as an example.
..1. remove outliers with outstanding slope
..Rejecting all lines with slope not in the range of a heuristic (-0.7) ± delta (0.2).
..2. extrapolate lines
..Extrapolate remaining lines to full height of the mask.
..3. remove outliers with outstanding position
..Since all remaining line have similar slope, I use mid points of the indicator of line position.
I removed all lines with x value not in the range of mean ± 2 * std.
..4. average all remaining lines and generate the final line

Repeat the same step for right lane with 0.7 as the heuristic for slope.

Final results:

Images

| ![solidWhiteCurve](test_images_output/solidWhiteCurve.jpg) | ![solidWhiteRight](test_images_output/solidWhiteRight.jpg) | ![solidYellowCurve](test_images_output/solidYellowCurve.jpg) |
|:---:|:---:|:---:|
| ![solidYellowCurve2](test_images_output/solidYellowCurve2.jpg) | ![solidYellowLeft](test_images_output/solidYellowLeft.jpg) | ![whiteCarLaneSwitch](test_images_output/whiteCarLaneSwitch.jpg) |

Videos: Please clone this repo and check them out at ./test_videos_output

### 2. Shortcomings

| ![error1](errors/error1.png) | ![error2](errors/error2.png) | ![error3](errors/error3.png) |

One potential shortcoming is t


### 3. Possible Improvements

A possible improvement would be to ...

Another potential improvement could be to ...
