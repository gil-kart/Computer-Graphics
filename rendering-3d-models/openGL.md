
welcome to my openGL project. in this project, I will present 3D model rendering using openGL.

the project is written in C++. 


Here you can see the code for my fragment shader. at this point, it only outpurs a constant color:
```c++
#version 330 core

struct Material
{
	sampler2D textureMap;
};

// We set this field's properties from the C++ code
uniform Material material;

uniform sampler2D texMap;

// Inputs from vertex shader (after interpolation was applied)	
in vec3 fragPos;
in vec3 fragNormal;
in vec2 fragTexCoords;
// The final color of the fragment (pixel)
out vec4 frag_color;

void main()
{
	vec3 textureColor = vec3(texture(material.textureMap, fragTexCoords));
	frag_color = vec4(vec3(0.f, 0.f, 1.f), 1.f)
}

```


In this part of the code (in the renderer class), I am passing the model view projection matrices from the renderer to the shader by setting the matching uniforms.

here is the main loop where it all happens:
```c++
if(cameraCount  > 0){
		int modelCount = scene.GetModelCount();
		const Camera& camera = scene.GetActiveCamera();
		for (int currentModelIndex = 0; currentModelIndex < modelCount; currentModelIndex++){
			// Activate the 'colorShader' program (vertex and fragment shaders)
			colorShader.use();		
			// Set the uniform variables
			colorShader.setUniform("model", world_trans * local_trans);
			colorShader.setUniform("view", view_2);
			colorShader.setUniform("light_position", light_trans);
			colorShader.setUniform("projection", projection_2);
			colorShader.setUniform("color", glm::vec3(0.2, 0.2, 0.8));
			colorShader.setUniform("material.textureMap", 0);
			colorShader.setUniform("camera_position", camera_tran);
			colorShader.setUniform("alpha", alpha);
			// Set 'texture1' as the active texture at slot #0
			texture1.bind(0);
			// Drag our model's faces (triangles) in fill mode
			glPolygonMode(GL_FRONT_AND_BACK, GL_FILL);
			glBindVertexArray(scene.GetModel(currentModelIndex).GetVAO());
			glDrawArrays(GL_TRIANGLES, 0, scene.GetModel(currentModelIndex).GetModelVertices().size());
			glBindVertexArray(0);

			// Unset 'texture1' as the active texture at slot #0
			texture1.unbind(0);
			
			// Drag our model's faces (triangles) in line mode (wireframe)
			glPolygonMode(GL_FRONT_AND_BACK, GL_LINE);
			glBindVertexArray(scene.GetModel(currentModelIndex).GetVAO());
			glDrawArrays(GL_TRIANGLES, 0, scene.GetModel(currentModelIndex).GetModelVertices().size());
			glBindVertexArray(0);
		}	
	}
  ```
  
 the attributes are being updated as soon as the model is being loaded, in the MeshModel constructor as you can see here:
 ```c++
 MeshModel::MeshModel(std::vector<Face> faces, std::vector<glm::vec3> vertices, std::vector<glm::vec3> normals, std::vector<glm::vec2> textureCoords, const std::string& modelName) :
	modelTransform(1),
	worldTransform(1),
	modelName(modelName)
{
	worldTransform = glm::mat4x4(1);
	std::random_device rd;
	std::mt19937 mt(rd());
	std::uniform_real_distribution<double> dist(0, 1);
	color = glm::vec3(dist(mt), dist(mt), dist(mt));

	modelVertices.reserve(3 * faces.size());
	for (int i = 0; i < faces.size(); i++)
	{
		Face currentFace = faces.at(i);
		for (int j = 0; j < 3; j++)
		{
			int vertexIndex = currentFace.GetVertexIndex(j) - 1;
			int normalIndex = currentFace.GetNormalIndex(j) - 1;
			Vertex vertex;
			vertex.position = vertices[vertexIndex];
			vertex.normal = vertices[vertexIndex];

			
			/*if(normalIndex < 501)
				vertex.normal = normals[776 - normalIndex];
			else
				vertex.normal = normals[500];
			*/
			if (textureCoords.size() > 0)
			{
				int textureCoordsIndex = currentFace.GetTextureIndex(j) - 1;
				vertex.textureCoords = textureCoords[textureCoordsIndex];
			}
			modelVertices.push_back(vertex);
		}
	}
	glGenVertexArrays(1, &vao);
	glGenBuffers(1, &vbo);

	glBindVertexArray(vao);
	glBindBuffer(GL_ARRAY_BUFFER, vbo);
	glBufferData(GL_ARRAY_BUFFER, modelVertices.size() * sizeof(Vertex), &modelVertices[0], GL_STATIC_DRAW);

	// Vertex Positions
	glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, sizeof(Vertex), (GLvoid*)0);
	glEnableVertexAttribArray(0);

	// Normals attribute
	glVertexAttribPointer(1, 3, GL_FLOAT, GL_FALSE, sizeof(Vertex), (GLvoid*)(3 * sizeof(GLfloat)));
	glEnableVertexAttribArray(1);

	// Vertex Texture Coords
	glVertexAttribPointer(2, 2, GL_FLOAT, GL_FALSE, sizeof(Vertex), (GLvoid*)(6 * sizeof(GLfloat)));
	glEnableVertexAttribArray(2);

	// unbind to make sure other code does not change it somewhere else
	glBindVertexArray(0);
}
```
after adjusting the code, here is the result. a blue beautiful cow:

![image](https://user-images.githubusercontent.com/73134488/107977139-52990d00-6fc3-11eb-8cf4-47e7785240de.png)


after implemnting the phong shading in the fragment shader, here is the result:

in all of the pictures, you can see the light's location (at the sliders on the right), and the camera's location (at the sliders on the left).
unless told different, the model is located at (0,0,0).

in this picture, you can see that the light is located over the horse's head and in front of the horse (at the point (0, 164, 164)).
![image](https://user-images.githubusercontent.com/73134488/107977780-5d07d680-6fc4-11eb-825d-f3b7afded927.png)

in this picture, I moved the light source to the left of the horse (the y and z coordinates stayd the same) to the point (-379, 164, 164).
![image](https://user-images.githubusercontent.com/73134488/107978291-3007f380-6fc5-11eb-8d05-9a003323bc16.png)

in this picture, I  moved the light behind the model, and above it (at the point (0, 315, -265).
![image](https://user-images.githubusercontent.com/73134488/107978521-93922100-6fc5-11eb-966f-524f57890180.png)

if we move up the camera and point it towards the horse (and leave the light source at the same location), we can see the light hits the horse's back. 
![image](https://user-images.githubusercontent.com/73134488/107978717-f2f03100-6fc5-11eb-9beb-554b8df52e59.png)

in this picture, the camera is located below and in fron of the horse. the light is also below it. the alpha component is smaller and thus, the light is brighter.
![image](https://user-images.githubusercontent.com/73134488/107979108-a1947180-6fc6-11eb-9911-1f859d37ed7b.png)


here are examples of directional light:

light from above: 
![image](https://user-images.githubusercontent.com/73134488/109136278-9f69aa00-7760-11eb-947d-1fda1670b5af.png)

light from below: 
![image](https://user-images.githubusercontent.com/73134488/109136393-bd370f00-7760-11eb-977b-05f51985905a.png)

light from the back:
![image](https://user-images.githubusercontent.com/73134488/109136502-dd66ce00-7760-11eb-9c33-acb86bf56de7.png)

and so on. 


the canonical projection I chose to implemnt is planner projection.

here are a few models with this projection:
teapot: 
![image](https://user-images.githubusercontent.com/73134488/108843709-bcc53980-75e3-11eb-951b-5aede727b0b9.png)


<!--- //![image](https://user-images.githubusercontent.com/73134488/107980182-7f9bee80-6fc8-11eb-8ec1-a3389ded779f.png)  -->

looking from above the teapot (the camera is lacted before and above the teapot, and pointed right at it):

![image](https://user-images.githubusercontent.com/73134488/108843846-eda56e80-75e3-11eb-8899-8f9dfc41951c.png)

<!--- //![image](https://user-images.githubusercontent.com/73134488/107980372-cd185b80-6fc8-11eb-8b0c-8d34109a3ae6.png) -->

camera model:
<!--- ![image](https://user-images.githubusercontent.com/73134488/107980887-b58da280-6fc9-11eb-9f4a-b22475925f79.png) -->
![image](https://user-images.githubusercontent.com/73134488/108844234-8340fe00-75e4-11eb-98ca-70982b95af99.png)

if we rotate the camera model on the x axis by 90 degrees, in a way that it's upper part will face us, this is what we see 
![image](https://user-images.githubusercontent.com/73134488/108844423-c7cc9980-75e4-11eb-9701-e3162dcbd2f0.png)


in all of this pictures, if we a imagine a page with black and white squares on it, being flattened on our models, the result we get is the result I showed in this task. 

for the task of finding a model with texture, i chose the model "spot". this is how it looks:
![image](https://user-images.githubusercontent.com/73134488/107983901-6ea2ab80-6fcf-11eb-8922-0047cef12780.png)

from some more angles: 
![image](https://user-images.githubusercontent.com/73134488/107984220-22a43680-6fd0-11eb-9f5e-41c66c805555.png)
![image](https://user-images.githubusercontent.com/73134488/107981840-8ed06b80-6fcb-11eb-93a6-331d192f72dc.png)

and here is a picture of another model!
![image](https://user-images.githubusercontent.com/73134488/107982179-3c437f00-6fcc-11eb-9b47-9bd3aedaf873.png)


I chose to implement toon shading. in the folowing exemples, you can see the definite level of Shading on the model. 

the color of the bunny is blue, the light is located to the right of the bunny. you can see in the picture 4 different levels of shaiding. 
![image](https://user-images.githubusercontent.com/73134488/107983148-fedff100-6fcd-11eb-9034-931ae6637345.png)

another example, with the light on the left, and the bunny rotated to the other side.
![image](https://user-images.githubusercontent.com/73134488/107983408-639b4b80-6fce-11eb-8e1a-f9d5474d36ae.png)

this is how it looks on a model with texture:
(the light is located right to the model)
![image](https://user-images.githubusercontent.com/73134488/107985365-a2330500-6fd2-11eb-9566-05c65b6a576e.png)

another example:
![image](https://user-images.githubusercontent.com/73134488/107986026-e4a91180-6fd3-11eb-9c25-d66398976c99.png)






