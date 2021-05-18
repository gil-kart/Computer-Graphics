1)
Replace the DrawTriangle function you implement in Assignment 1 by a function that
fills the entire triangle. You can use any of the approaches we discussed in class. Place
a model in the scene and place it such that it is clearly visible. Pick a random color for
every triangle and place a screenshot of the result in your report. This picture is usually
refered to as the
colorbuffer
. Note that you will see triangles overlapping; triangles in
the back might be occluding triangles in the front

I replaced the DrawTriangle function with ColorTrinagle function that fills the entire triangle.

for every trinagle the function recieves, the function finds the given triangle's bounding box, and in a nested loop, find all the pixels that are within the triangle.

here is a screen shot of a bunny, being drawn by the ColorTrinagle function:

![image](https://user-images.githubusercontent.com/73134488/103201327-5334f180-48f8-11eb-8b86-078cc0a18c4e.png)

something looks a bit weird about this bunny.

we can see that if we are spinning it arohund the Y axis, his head is being drawn first. that is because the triangles that makes its head are over lapping.

![image](https://user-images.githubusercontent.com/73134488/103201574-d6564780-48f8-11eb-9ce3-3a5afcc93160.png)

in the next task we will fix this problem.

2)
Implement the z-buffer algorithm. The issue mentioned above should not occur anymore.
The z-buffer can be visualized as a grey scale image (as in the lecture). Show side-by-side
pictures of the color buffer and z-buffer, for several models or viewpoints.

afer adding the Zbuffer class, and calculating the Z buffer for each pixel, here's the result:

![image](https://user-images.githubusercontent.com/73134488/103458403-507b3780-4d10-11eb-9725-a4f19494f6f1.png)

we can see that if we spin the bunny, we can see his tail but we can't see his face (the result we wanted).

![image](https://user-images.githubusercontent.com/73134488/103458437-d0a19d00-4d10-11eb-97e2-023d16f3984b.png)

here is a visualization if a grey scale image being showed side-by-side:

the camera is at the point (0,0,386). 

the bunny that has a blacker color, is at the point (0,0,151). 

the bunny that has a grayer color, is at the point (0,0,-331).

![image](https://user-images.githubusercontent.com/73134488/103458964-ae118300-4d14-11eb-86a4-a7edff080e9d.png)

we can see that if the bunny is closer to the screen, it becomes more dark. if it's far from the screen it becomes more gray.

here's the bunny (on the right) at the point (0,0,-700). 
and the bunny (on the left) at the point (0,0,-1000).

![image](https://user-images.githubusercontent.com/73134488/103459138-92f34300-4d15-11eb-96f2-90510667e572.png)
 
here's the same effect with the banana model:

![image](https://user-images.githubusercontent.com/73134488/103459264-b1a60980-4d16-11eb-9c98-b88d71d3b4ff.png)



