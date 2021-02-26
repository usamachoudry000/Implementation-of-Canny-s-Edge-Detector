I will explain block by block code in this file:
1-In first block i import libraries 
2-In next 2 blocks i read image from data set folder and plot it after resize image into 120x120.
3-In 4th block i convert image into gray scale
4-In 5th block i create convolution function to convolve image and filter of any size and return result after convolution.
in this block width and height is representing image size and f_width and f_height is representing filter width and height.
There are four nested loops the outer loop r and c will move on every index of image and inner loop m and n is filter that will move up down top and bottom
in image after generating values i replace at middle of every filter locatio in image.Last loop is representing replacement of computed values.
5-In 6th,7th and 8th block i am taking sigma and value of T and passing to Calculate filter size and Calculate gradient.Calculate filter is returning
X and Y filter after that i pass these x and y into calculate gradent that is generating G(x,y),fx and fy. fx is derivative of gaussian filter w.r.t to x
and fy is derivative of gaussian filter w.r.t y.
6-In 8th,9th and 10th block i am applying these mask Gxy,fx and fy on image and showing and saving into result folder.
7-In 11th block i am computing gradient using formula of sqrt(fx^2+fy^2).these two fx and fy are computed after applying the filter of fx and fy.
8- In 12th block i am computing gradient direction using thete arctan2 formula.it will generate some negative angle so i will add 360 on that index who is less than 0.
9-In 13th block i am generating Non Maxima supression in which i am using theta that i generated in previous step and taking Magnitude(x,y) and checking the angle and comparing next 
and previous values with M(x,y). if angle is 0 to 22.5 and 157.5 to 202.5 and 337.5 to 360 i am checking horizontally next and previous.In next steps i am checking according to angle
like if angle is near by 45 degree i will check diagnoly and if angle is 90 i will check vertical and so on.
After that i am ploting it. it will thin edges.
10-In 10th step i am computing hysteresis thresholding in which i am setting TH and TL and also taking 2D array that consist of zeros.
I am comparing left to right and top to bottom every index with TH if andex is greater than TH and unvisited it will check it neighbors if neighbors index are not visited before and 
neigbhors are greater tha TL i will add edge at that point and mark it visited.After that i plot it with different values of TH and TL with different sigma values
