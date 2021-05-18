
 ### point light source:
 
 in the picture, the triangle with red green and blue edges is a point light source.
 
 the user ca control the light's location on the screen by using the sliders. each slider controls a different axis.
 
 also, the user can control the light's  ambient, diffuse and specular reflections by using the mouse and choosing a color for each reflection. 
 
 this is how it looks (the model is showen in flat shading),
 
 the camera is located at (0,0,500), the model is located at the origin and the light source's location is writen on the sliders:
 
 ![image](https://user-images.githubusercontent.com/73134488/104090224-fb927080-527d-11eb-94bf-9422c6e2a496.png)

 in adittion, the user can choose the alpha component, that affects the light's  brightness. you can see a comparison in these three pictures
 
 here, hlpha is equal to 0.437, and the bunny looks prety bright.
 
 ![image](https://user-images.githubusercontent.com/73134488/104092097-6184f500-528a-11eb-8d47-6874cbe40660.png)

here, hlpha is equal to 1 and the bunny looks darker:

![image](https://user-images.githubusercontent.com/73134488/104092126-9a24ce80-528a-11eb-969a-f073a6153056.png)

here, hlpha is equal to 4 and the bunny looks even more dark:

![image](https://user-images.githubusercontent.com/73134488/104092151-c2acc880-528a-11eb-8f6d-bf5fcecaefeb.png)




now let's look at some rotation:
 
 the user can use the rotate sliders in order to rotate the light source around the x, y, z and axises. 
 
 here is an example of a few pictures showing the light, rotating around the model (around the y axis):
 
 0 degrees rotation:
 ![image](https://user-images.githubusercontent.com/73134488/104090456-9770ac00-527f-11eb-8a00-6de8126ea28e.png)

90 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/104090488-d0108580-527f-11eb-9905-22a416588510.png)

180 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/104090506-e880a000-527f-11eb-9d77-4245c84a42e5.png)

270 degrees rotation:
![image](https://user-images.githubusercontent.com/73134488/104090525-03ebab00-5280-11eb-8afc-65193b7942c2.png)


 ### parallel light source:
 
 in my code, to keep things simple and intuitive, the user can choose the parallel light source's direction( above, below, left, right, or from the front or back)
 
 also, the user can choose the light's ambient, diffuse and specular reflections the same way as the point light's reflections.
 
 here are a few examples of the parallel light in a differnt model
 
 parallel light from above:
 
 ![image](https://user-images.githubusercontent.com/73134488/104091295-2f24c900-5285-11eb-84c8-6fa0f7098ac9.png)

 parallel light from below:
 
![image](https://user-images.githubusercontent.com/73134488/104091316-4ebbf180-5285-11eb-8e49-12f4e6847b47.png)

 parallel light from the left:
 
 ![image](https://user-images.githubusercontent.com/73134488/104091358-9478ba00-5285-11eb-8313-be85e3df75a0.png)

 parallel light from the right:
 
 ![image](https://user-images.githubusercontent.com/73134488/104091376-b2deb580-5285-11eb-9eb4-974b3dea5374.png)

 parallel light from the back (of the model):
 
 ![image](https://user-images.githubusercontent.com/73134488/104091396-d99cec00-5285-11eb-9142-356a4c0d3a46.png)

 

  I added the possibilty to choose the model's material. 
  
  the user can choose with the mouse the valuse for ambient diffuse and specular reflections.

 this is how it looks in these pictures:
 
 bunny
 ![image](https://user-images.githubusercontent.com/73134488/104092323-e6bcd980-528b-11eb-9d11-0d552075bda1.png)

pawn
![image](https://user-images.githubusercontent.com/73134488/104092570-7d3dca80-528d-11eb-837d-13805b89193f.png)

green bishop with red light
![image](https://user-images.githubusercontent.com/73134488/104092705-5fbd3080-528e-11eb-8369-9a5b4811c389.png)


  I am now going to present the bunny model, shown in  flat, Gouroad and Phong shading.
  
  bunny in flat shading:
  
  ![image](https://user-images.githubusercontent.com/73134488/104092893-a19aa680-528f-11eb-9241-6fe82cd04a79.png)

  bunny in Gouroad shading:
   
   ![image](https://user-images.githubusercontent.com/73134488/104092907-c0993880-528f-11eb-9980-a82c1ae326c7.png)
  
  bunny in Phong shading:
  
  ![image](https://user-images.githubusercontent.com/73134488/104092933-e32b5180-528f-11eb-95cb-4d0cad814ebf.png)


  #4)
  Pick  a  model  and  clearly  demonstrate  that  all  of  the  lighting  and  shading  capabilities have been implemented.  
  Add the relevant screenshots to the report and explain what is shown in each picture.
  
  the model I chose was the bunny model. for each shading option(flat, Gouroad and Phong) I am going to demonstrate the lighting  and  shading  capabilities have been implemented.
  
  in all of the shading options, the buuny is located at the origin, our camera is located at (0,0,500), unless told different.

  
  ### flat shading:
  
  at question 1, I already showed the parallel light source options for flat shading, so now I am going to show the capabilities have been implemented on flat shading with point light source:
  
  here is a blue bunny.
  
  the colorfull trinagle is the light source that's located at (0,0,251)
  
  ![image](https://user-images.githubusercontent.com/73134488/104103537-4c6c8e00-52ab-11eb-9037-b62b6e1c5342.png)
 
 we can see in the next picture, that of we take the light source to the left(by translating it on the negetive dirction of the x axis), the right side of the bunny becomes darker. 

 ![image](https://user-images.githubusercontent.com/73134488/104103619-c43ab880-52ab-11eb-97f1-d582ce08e956.png)
 
 if we take the light source and put it underneath the bunny (by translating it on the negetive y axis), we can see that the bunny's belly becomes brighter because it's facing to the light source.
 
 ![image](https://user-images.githubusercontent.com/73134488/104103749-6f4b7200-52ac-11eb-83c0-fa11af219203.png)

in this picture we can see that if we rotate the bunny by 55*  on the y axis, and locate the light over the bunny (by translating it on the positive y axis),
the upper side of the bunny becomes bright.

 ## gouroade shaidng

### point light source

here is the bunny  with the same 55* rotation on the y axis, and the light located above it

![image](https://user-images.githubusercontent.com/73134488/104104161-0f09ff80-52af-11eb-82c0-fe98776a9801.png)

in this picture, we can see the bunny without any rotation and the light is located above the bunny and close to the camera at the point (0, 102,198).

![image](https://user-images.githubusercontent.com/73134488/104104351-1ed61380-52b0-11eb-88b1-c3e7ef000bd3.png)

we can see that the bunny is a bit bright. we can change it by increasing the alpha component. this will give us a darker bunny.

![image](https://user-images.githubusercontent.com/73134488/104104367-3ca37880-52b0-11eb-9292-172fb7dfd87f.png)


here is the bunny with the light on it's right side

![image](https://user-images.githubusercontent.com/73134488/104104414-b471a300-52b0-11eb-8232-cc9e11f1f334.png)

this is a picture the light below the bunny and close to the camera

![image](https://user-images.githubusercontent.com/73134488/104104440-dc610680-52b0-11eb-9ffb-069ad3f1e774.png)


### parallel light source

this is a picture with a parallel light from above

![image](https://user-images.githubusercontent.com/73134488/104104557-8e003780-52b1-11eb-8e69-5ec8d927f2c4.png)

this is a picture with a parallel light from below

![image](https://user-images.githubusercontent.com/73134488/104104621-f0593800-52b1-11eb-8364-6670a7eb6d69.png)

this is a picture with a parallel light from right

![image](https://user-images.githubusercontent.com/73134488/104104652-1bdc2280-52b2-11eb-82f0-0a5ee692c0a5.png)

and the same concept reapets it self with the other directions.


 ## phong shaiding
 ### point light source
 here is a picture of the bunny with the light above it and close to the camera
 
 ![image](https://user-images.githubusercontent.com/73134488/104104986-f3edbe80-52b3-11eb-988d-15e9838303be.png)

this is the with 55* roatation and the light close to the camera. 

![image](https://user-images.githubusercontent.com/73134488/104105117-c2c1be00-52b4-11eb-9458-70fe7c2c3835.png)


this is a picture of the bunny with 55* roatation and the light located below the bunny annd close to the camera.

![image](https://user-images.githubusercontent.com/73134488/104105160-04eaff80-52b5-11eb-88ca-f0a87d29d2ca.png)

this is a picture of the camera located at (0,462, 397) and pointed at the origin. the bunny is located at the origin.

the light is located at (0,255,0) just above the bunny.

![image](https://user-images.githubusercontent.com/73134488/104105388-62338080-52b6-11eb-8942-41509a7c4ca1.png)


## parallel light source

the parallel light comes from above

![image](https://user-images.githubusercontent.com/73134488/104106303-631be080-52bd-11eb-9a79-6be207e94512.png)

the parallel light comes from below

![image](https://user-images.githubusercontent.com/73134488/104106329-85156300-52bd-11eb-86c8-bdc55cb05a50.png)

the parallel light comes from behind

![image](https://user-images.githubusercontent.com/73134488/104106349-a7a77c00-52bd-11eb-8740-0b5829b8e57d.png)

and so on.


before we start the fog, this is the image we see. the upper triangle (with red blue and green edges) is a point light source thats located at (0,63,224).

the lower triangle(with pink, yellow and light blue edges) is just a triangle at the origin)

the purple chain is located at (-73,0,0), on the chain's left.

![image](https://user-images.githubusercontent.com/73134488/104107022-2dc5c180-52c2-11eb-8390-172eaa87cd1a.png)

this is a picture that shows the result of exponential fog effect, we can see that thee triangles and chain are pretty fogy.

![image](https://user-images.githubusercontent.com/73134488/104107123-ce1be600-52c2-11eb-9426-2cba13354a39.png)

we can see that if we translate the purple chain on the negetive z axis, it becomes grayer. the chain in this picture is located at (-73,0,-400).

![image](https://user-images.githubusercontent.com/73134488/104107198-32d74080-52c3-11eb-9720-a670f4862123.png)


and grayer.  the chain in this picture is located at (-73,0,-800).

![image](https://user-images.githubusercontent.com/73134488/104107250-88135200-52c3-11eb-9f0a-eac02dd17378.png)

we can see that if we scale the chain to be bigger but still leave it at the point (-73,0,-800), it's still the same gray color.

![image](https://user-images.githubusercontent.com/73134488/104107332-fb1cc880-52c3-11eb-947a-b995ed63f24a.png)


