# A Realtime Video Stabilization
This program works like an EIS (Electronic Image stabilaization), Originally the project was made to detect and work as a document scanner.
This program checks for any avaliable camera devices that are attacted to the computer (web camera in my case), if available, it then uses it. The program then goes into an infinite loop treating 1 millisecond as one frame (though this doesnt happen due to delay created by the processor) and treating that frame as an image. Then we apply the Preprocessing of the image, then we get the Contours, then we Warp the image and display the image in another window. This process happens continuously such that the effect at large scale is treated as a videa rather than image


* Preprocessing Step  
  * Convert the raw image to gray scale (cvtColor())  
  * Convert the gray scale image to blurred image (GaussionBlur())  
  * Convert the blurred image to a canny image (canny is used to detect the edges) (Canny())  
  * Covert the canny image to a dilated canny image (dilate())  

  
* Getting the Contours (Shape detection)  
  * Finding the Contours (shapes) in the dilated canny image (findCotours())  
  * Finding the area of the shapes found in the image (contourArea())  
  * Filtering the shapes for a threshold area  
  * Optional: Draw Contours around the shape (drawContours())  
  * Finding the number of points in a given shape   
  * Optional: Draw the Contours around the shape by using the point reference  
  * Filtering the shapes by number of points and max area of a shape (rectangles are filtered in)  
  * Return the points of the biggest rectange 

* Warpping the image
  * Wrapping the by considering the givern points (warpPerspective()) 
  * The final wrapped image then displayed onto a seperate window 
