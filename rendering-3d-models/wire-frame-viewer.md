In this part of the project I will present 3D models, showen in a wire-frame shape


I chose the bunny model. at first I put the bunny at the origin, and then, I moved it 62 units on the positive direction of the Z axis, using the local translation.

the camera is located 500 units on the positive direction of the Z axis, and zero on the x and y axis.

this way, we can have a nice good look at the bunny: 

![image](https://user-images.githubusercontent.com/73134488/101262863-3b7baa80-374a-11eb-87e1-1c18dab5a382.png)

then, I rotated the bunny around the Y axis, using the world rotation, so we can see how the bunny is circeling the Y axis. here are the results:

45 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101262997-e68c6400-374a-11eb-803c-a9793896b56d.png)

90 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263056-5a2e7100-374b-11eb-92de-4a5878a98185.png)

135 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263145-ca3cf700-374b-11eb-950b-9e5fd9fcebf9.png)

180 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263169-f193c400-374b-11eb-82e6-800acef38b87.png)

225 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263198-29027080-374c-11eb-8dd2-cd4e3f0c7059.png)

270 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263219-53ecc480-374c-11eb-9118-a455f3cd8f37.png)

315 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101263273-ba71e280-374c-11eb-94ff-c60b476e8a8d.png)

360 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/101264026-19cff280-374d-11eb-862f-d01660f7448e.png)

---------------------------



In here, we can see a banana model with two types of transformations: T1, T2.

the transformations are:

T1 = translating 90 units on the negetive Y direction

T2 = rotating 90 units on the positive Z direction

At the start, the model is located at the origin (0,0,0) and the camera is located 250 units on the positive direction of the z axis and 0 on the x and y axis (0,0,250).

so before any transformation it looks like this:

![image](https://user-images.githubusercontent.com/73134488/101266638-71745b00-3759-11eb-8e92-779e7cfefde8.png)

 applying T1 in model frame and T2 in world frame:
![image](https://user-images.githubusercontent.com/73134488/101266693-f9f2fb80-3759-11eb-8127-bc1db180fff7.png)

applying T1 in world frame and T2 in model frame:
![image](https://user-images.githubusercontent.com/73134488/101266843-7e924980-375b-11eb-9ec0-095bc41f089f.png)

---------------------------


Displaying a bounding box for the model: 
bounding box (in purple):
![image](https://user-images.githubusercontent.com/73134488/101278947-68ba6e00-37c7-11eb-8b52-be8dbc7444e9.png)

translating the model in the x dirction:

![image](https://user-images.githubusercontent.com/73134488/101278989-b7680800-37c7-11eb-9f46-6d949c1b03b3.png)


Displaying the face normals:
![image](https://user-images.githubusercontent.com/73134488/101278246-cc8e6800-37c2-11eb-8081-98d9852e1d16.png)

translating the model in the x dirction:
![image](https://user-images.githubusercontent.com/73134488/101278324-360e7680-37c3-11eb-8557-bb711c47a42d.png)


Displaying the vertex normals:

![image](https://user-images.githubusercontent.com/73134488/101278895-14af8980-37c7-11eb-9855-0aeb8c59baca.png)

translating the model in the x dirction:

![image](https://user-images.githubusercontent.com/73134488/101278917-34df4880-37c7-11eb-911c-8d16da198ba5.png)


---------------------------

## Here, I am setting the camera away from the model and comparing the orthographic projection vs. the perspective projection.



I've put the camera away from the model (by moving it on the positive z direction) and pushed the model away from the camera( by moving it on the negetive z direction).

this is how it looks in perspective projection: 
![image](https://user-images.githubusercontent.com/73134488/101266988-d8474380-375c-11eb-848b-de0510409292.png)

this is how it looks in orthographic projection:
![image](https://user-images.githubusercontent.com/73134488/101267082-c914c580-375d-11eb-81ee-2caf87db6833.png)

---------------------------

## Now, I am goin to set the projection to perspective and show the difference between changing the zoom (by changing the size of the frustum) and moving closer or farther from the model.

### first, we put the camera at (0,0,2.5) so we could look at the object. 

![image](https://user-images.githubusercontent.com/73134488/101270364-ec9d3780-3780-11eb-96d9-a500608f0806.png)

### we can notice that if we take the camera back (on the positive z dircetion), our object will be closer an closer to the midle of the screen:

![image](https://user-images.githubusercontent.com/73134488/101270398-56b5dc80-3781-11eb-8572-737a1a668344.png)

![image](https://user-images.githubusercontent.com/73134488/101270406-6fbe8d80-3781-11eb-9885-f0309f228594.png)
#### but if we bring back our camera to (0,0,2.5) and increase or decrease our fovy parameter we will get a different outcome:

### increasing the fovy: 
![image](https://user-images.githubusercontent.com/73134488/101270447-c0ce8180-3781-11eb-89d3-72184b490b28.png)

![image](https://user-images.githubusercontent.com/73134488/101270452-e65b8b00-3781-11eb-8f2d-5a6c9429f459.png)
### decreasing the fovy: 

![image](https://user-images.githubusercontent.com/73134488/101270480-228eeb80-3782-11eb-9e28-6dd16a8d08b8.png)

when we change the fovy paramater, we change the size of the view volume. for that reason, if we decrease the size of the view volume, the objects that are still inside the view volume will be bigger. if we increase the view volume, the objects inside the view volume will look smaller.  
---------------------------
Now, I will Rotate the camera in the camera’s frame around the y (up) axis, in a way that the model is 
 placed close to the edge of the screen. than I will Compare the result vs. rotating the camera in the world frame

For starters, I placed the camera far from the object at the positive direction of the z axis.

after that, I moved the model on the negetive  direction of the x axis, sp the model will be close to the edge of the screen.

so we get this: 
![image](https://user-images.githubusercontent.com/73134488/101267770-37a95180-3765-11eb-9a8a-dbad3a60be94.png)

after it, I started to rotate the camera's frame around the y axis, using the GUI I desgined. here are some screen shots that shows the rotation of the camera's frame 
until the model is out of the frame:
![image](https://user-images.githubusercontent.com/73134488/101267841-0ed58c00-3766-11eb-8949-896b0133b7bf.png)

![image](https://user-images.githubusercontent.com/73134488/101267874-59ef9f00-3766-11eb-92c3-6516b08c3e04.png)

![image](https://user-images.githubusercontent.com/73134488/101267905-a63adf00-3766-11eb-9d60-1de665be1bd3.png)

![image](https://user-images.githubusercontent.com/73134488/101267917-c8346180-3766-11eb-8983-06aa47b91ffc.png)

![image](https://user-images.githubusercontent.com/73134488/101267930-e0a47c00-3766-11eb-9cd7-a2d6da7337da.png)

and the model is out of the frame:
![image](https://user-images.githubusercontent.com/73134488/101268046-d171fe00-3767-11eb-82b1-9fdda1b7711e.png)


when complete 180 degrees, as expected, we get the model "upside down": 
![image](https://user-images.githubusercontent.com/73134488/101268083-2150c500-3768-11eb-9026-01e621c361c0.png)

until it's  almost out: 
![image](https://user-images.githubusercontent.com/73134488/101268103-4e04dc80-3768-11eb-9859-4655ff8b0b68.png)

when we complete 360 degrees we get the model again:
![image](https://user-images.githubusercontent.com/73134488/101268128-80aed500-3768-11eb-810a-9236e4eb18d8.png)

## this is the result for rotating the camera in the world frame. 

0 degrees

![image](https://user-images.githubusercontent.com/73134488/101268267-c6b86880-3769-11eb-8fb9-584960c31ea4.png)

58 degrees

![image](https://user-images.githubusercontent.com/73134488/101268276-e354a080-3769-11eb-8aee-3b36c3b5bbb8.png)

90 degrees

![image](https://user-images.githubusercontent.com/73134488/101268296-172fc600-376a-11eb-8f99-6f7d8bab2703.png)

116 degrees

![image](https://user-images.githubusercontent.com/73134488/101268319-4cd4af00-376a-11eb-89ae-ecb49c94d0fa.png)

166 degrees

![image](https://user-images.githubusercontent.com/73134488/101268348-860d1f00-376a-11eb-90e3-0822f3266e49.png)

201 degrees

![image](https://user-images.githubusercontent.com/73134488/101268374-b48afa00-376a-11eb-9cc7-80a26feb1ca7.png)

261 degrees

![image](https://user-images.githubusercontent.com/73134488/101268384-d71d1300-376a-11eb-89c2-fd341bba6814.png)

325 degrees

![image](https://user-images.githubusercontent.com/73134488/101268402-0895de80-376b-11eb-8e94-2dda5032934d.png)

360 degrees

![image](https://user-images.githubusercontent.com/73134488/101268415-2400e980-376b-11eb-9a52-58aa91772ac4.png)

---------------------------
## Now, will Set the camera position to (177, 177, 177) and orient it towards the origin using LookAt function. 

I've put the model at the origin and placed the camera in (177,177,177). after that I oriented the camera at the origin using look at and this is what I got:

![image](https://user-images.githubusercontent.com/73134488/101268501-4d6e4500-376c-11eb-9426-932db5615aef.png)
---------------------------

##  Here's a screenshot showing as much of the GUI as possible

I've put a few check boxes, some of the check boxes open new window with sliders that help the user control the transformaion performing on the model.

![image](https://user-images.githubusercontent.com/73134488/101268619-dcc82800-376d-11eb-8296-0e69e06c0ede.png)

for exemple, if the user presses the local translate check box, a new window opens up with sliders that determine the x,y,z cordinates of the object.

![image](https://user-images.githubusercontent.com/73134488/101268688-d8e8d580-376e-11eb-8db8-adda7e7d24e5.png)
---------------------------
