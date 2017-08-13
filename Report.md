**Finding Lane Lines on the Road- P1** 

This Report explains the proposed algorithm for finding Road Lane under diffrent lighting condition and shadow reflection that form arbitrary shape(ex:tree reflection). 


---

**Method and Project Algorthim Reflection**

The project aim is detecting Lane line in road regardless the color of the lane as it differ from country to other. Also the proposed work addressed to enhance the frame against the light reflection. Many techniques in Image Processing enhancement has conducted such as analyze the histogram equalization for HLS space and norm the histogram. However , in some frames the amount of light was strong. HLS color space has chosen because it has the ability to analyze the image color against the amount of Light. Other method was investigated but not conducted (shape from shadow , the gradient of the image)as the shadow reflect arbitrary shape and the following are the followed pipeline:


* Resize the Image to fit all test videos sizes.
![alt text][Frame]
* Extract a trapezoidal region of interest and the vertices assume the camera mounted in position in challenge video.
![alt text][ROI]
* The current frame enhanced by setting the Hue channel to zero and analyze the L and S channel together.
![alt text][iHSL]
![alt text][iSL]
![alt text][iBGR]
* Bilateral Filter was chosen due to it's efficiency to sharp the edges , the filter with higher values might     eliminate the lane in the high amount of light either for solid yellow line or striped white line
![alt text][Filtered]

* Canny edge detection
![alt text][edges]
* The line detection was developed using Hough Transform , and classifying the Right and Left lines was by the   slope  if (slope>.5) so it is left and id (slope <-5) its right line. this classification ignore the           horizontal line and line with high slope. 
* To not draw all the detected lines individually , averaging the lines' points was necessary to form one         single solid line for each side
* The current frame's lines are stored in previous line in order to if the lines weren't detected in high noise   ,the lines will be the previous line (in red color) as lines position across the frame doesn't change too       much.
* Lines are drawn in separate function (draw_lines) to just draw the passed lines.
* Last step is to draw the detected line on the original frame. 
![alt text][Result]



[Frame]: ./imagesR/frame.png
[ROI]: ./imagesR/ROI.png
[iHSL]: ./imagesR/HSL.png
[iSL]: ./imagesR/SL.png
[iBGR]: ./imagesR/ImageProc.png
[Filtered]: ./imagesR/filtered.png
[edges]: ./imagesR/edges.png 
[Result]: ./imagesR/result.png



---



**Potential shortcomings**
This solution detect the lane in each frame in the challenging video except 4 frames. By decreasing the Hough votes it can detect the lane in each frame but other small lines will be detected in area that has high shadow noise. Also the drawn lines are shaking depend on the location of the Lane in each frame. The performance of the system might be influenced by other lighting condition

**Suggest possible improvements to your pipeline**

This algorithm can be improved by enhance the histogram either in dark side or bright side. as by decrease the bright range to be in darker side and increase the dark range to brighter rage so that the two histogram peaks be aligned in same histogram range. but I find difficulty to modify part of histogram to another range.**Finding Lane Lines on the Road- P1** 

This Report explains the proposed algorithm for finding Road Lane under diffrent lighting condition and shadow reflection that form arbitrary shape(ex:tree reflection). 


---

**Method and Project Algorthim Reflection**

The project aim is detecting Lane line in road regardless the color of the lane as it differ from country to other. Also the proposed work addressed to enhance the frame against the light reflection. Many techniques in Image Processing enhancement has conducted such as analyze the histogram equalization for HLS space and norm the histogram. However , in some frames the amount of light was strong. HLS color space has chosen because it has the ability to analyze the image color against the amount of Light. Other method was investigated but not conducted (shape from shadow , the gradient of the image)as the shadow reflect arbitrary shape and the following are the followed pipeline:


* Resize the Image to fit all test videos sizes.
![alt text][Frame]
* Extract a trapezoidal region of interest and the vertices assume the camera mounted in position in challenge video.
![alt text][ROI]
* The current frame enhanced by setting the Hue channel to zero and analyze the L and S channel together.
![alt text][iHSL]
![alt text][iSL]
![alt text][iBGR]
* Bilateral Filter was chosen due to it's efficiency to sharp the edges , the filter with higher values might     eliminate the lane in the high amount of light either for solid yellow line or striped white line
![alt text][Filtered]

* Canny edge detection
![alt text][edges]
* The line detection was developed using Hough Transform , and classifying the Right and Left lines was by the   slope  if (slope>.5) so it is left and id (slope <-5) its right line. this classification ignore the           horizontal line and line with high slope. 
* To not draw all the detected lines individually , averaging the lines' points was necessary to form one         single solid line for each side
* The current frame's lines are stored in previous line in order to if the lines weren't detected in high noise   ,the lines will be the previous line (in red color) as lines position across the frame doesn't change too       much.
* Lines are drawn in separate function (draw_lines) to just draw the passed lines.
* Last step is to draw the detected line on the original frame. 
![alt text][Result]



[Frame]: ./imagesR/frame.png
[ROI]: ./imagesR/ROI.png
[iHSL]: ./imagesR/HSL.png
[iSL]: ./imagesR/SL.png
[iBGR]: ./imagesR/ImageProc.png
[Filtered]: ./imagesR/filtered.png
[edges]: ./imagesR/edges.png 
[Result]: ./imagesR/result.png



---



**Potential shortcomings**
This solution detect the lane in each frame in the challenging video except 4 frames. By decreasing the Hough votes it can detect the lane in each frame but other small lines will be detected in area that has high shadow noise. Also the drawn lines are shaking depend on the location of the Lane in each frame. The performance of the system might be influenced by other lighting condition

**Suggest possible improvements to your pipeline**

This algorithm can be improved by enhance the histogram either in dark side or bright side. as by decrease the bright range to be in darker side and increase the dark range to brighter rage so that the two histogram peaks be aligned in same histogram range. but I find difficulty to modify part of histogram to another range.**Finding Lane Lines on the Road- P1** 

This Report explains the proposed algorithm for finding Road Lane under diffrent lighting condition and shadow reflection that form arbitrary shape(ex:tree reflection). 

---

**Method and Project Algorthim Reflection**

The project aim is detecting Lane line in road regardless the color of the lane as it differ from country to other. Also the proposed work addressed to enhance the frame against the light reflection. Many techniques in Image Processing enhancement has conducted such as analyze the histogram equalization for HLS space and norm the histogram. However , in some frames the amount of light was strong. HLS color space has chosen because it has the ability to analyze the image color against the amount of Light. Other method was investigated but not conducted (shape from shadow , the gradient of the image)as the shadow reflect arbitrary shape and the following are the followed pipeline:


* Resize the Image to fit all test videos sizes.

![alt text][Frame]

* Extract a trapezoidal region of interest and the vertices assume the camera mounted in position in challenge video.
![alt text][ROI]

* The current frame enhanced by setting the Hue channel to zero and analyze the L and S channel together.

![alt text][iHSL]
![alt text][iSL]
![alt text][iBGR]

* Bilateral Filter was chosen due to it's efficiency to sharp the edges , the filter with higher values might     eliminate the lane in the high amount of light either for solid yellow line or striped white line

![alt text][Filtered]

* Canny edge detection

![alt text][edges]

* The line detection was developed using Hough Transform , and classifying the Right and Left lines was by the   slope  if (slope>.5) so it is left and id (slope <-5) its right line. this classification ignore the           horizontal line and line with high slope. 
* To not draw all the detected lines individually , averaging the lines' points was necessary to form one         single solid line for each side
* The current frame's lines are stored in previous line in order to if the lines weren't detected in high noise   ,the lines will be the previous line (in red color) as lines position across the frame doesn't change too       much.
* Lines are drawn in separate function (draw_lines) to just draw the passed lines.
* Last step is to draw the detected line on the original frame. 

![alt text][Result]



[Frame]: ./imagesR/frame.png
[ROI]: ./imagesR/ROI.png
[iHSL]: ./imagesR/HSL.png
[iSL]: ./imagesR/SL.png
[iBGR]: ./imagesR/ImageProc.png
[Filtered]: ./imagesR/filtered.png
[edges]: ./imagesR/edges.png 
[Result]: ./imagesR/result.png



---
**Potential shortcomings**
This solution detect the lane in each frame in the challenging video except 4 frames. By decreasing the Hough votes it can detect the lane in each frame but other small lines will be detected in area that has high shadow noise. Also the drawn lines are shaking depend on the location of the Lane in each frame. The performance of the system might be influenced by other lighting condition

**Improvment suggestions **

This algorithm can be improved by enhance the histogram either in dark side or bright side. as by decrease the bright range to be in darker side and increase the dark range to brighter rage so that the two histogram peaks be aligned in same histogram range. but I find difficulty to modify part of histogram to another range.