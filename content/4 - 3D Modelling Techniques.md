
"Paaaaaaperbaaack wriiiiteeeer! (Paaaaaaperbaaack wriiiiteeeer!) (Paaaaaaperbaaack wriiiiteeeer!)"
<sub>The Beatles - Paperback Writer</sub>


Quite a bit to take in here, so let's index everything.


- Design Principles
	- Form
	- Contrast
	- Balance
	- Proportion
- Common 3D Concepts
	- Common 3D Object Types
	- Primitive Objects
	- The Pivot Point
	- Transform Tools
	- Editing Tools
	- Topology
- Materials & Textures
	- Materials
	- What Are UVs?
	- Textures



# Part 1 - Design Principles

Long ago, four nations lived in harmony... yeah, we're not doing that again.


## Form
A form is, essentially, a **3D shape**, like a cube, sphere, cone, etc. A 3D form can be any shape, complex and simple, however it is important to remember that **these complex shapes are always just a combination of simple shapes.** Any form in 3D can be recreated with simple shapes.

## Contrast
Contrast is when two opposing elements are present in your art piece. Using a **variety** of shapes, textures and materials can create contrast. This can generate interest or draw a viewer's eye directly to your work.


## Balance
This is the concept of **visual equilibrium**. Essentially, Newton's 3rd Law: Every action must have a reaction. When the action and reaction are balanced, this creates a visual stability.

This balance is simple: If it is balanced, it stays. If not, it tips over.

A scene that is unbalanced may not be nice to look at for some people. Of course, this doesn't matter if this is what you want. But, seeing as how this is our first "art" module, I recommend we stay in the basics before moving onto the more complicated, abstract stuff.

Anyway, there are two types of balance: **Symmetrical and Asymmetrical**.


### Symmetrical
You can get a symmetrical balance by having equal visual units placed on opposite sites of an imaginary "center point". 

This is usually the easiest balance to achieve. It invokes a sense of stability, permanence and calm.

### Asymmetrical
This is achieved by placing **dissimilar visuals**, with **different visual interests**. An example of this is placing multiple smaller visuals on one side, balancing with one large object on the other.

![[Pasted image 20241126203613.png]]





## Proportion
This refers to elements being compared to one another in terms of size, quantity and degree of emphasis. Basically, it is the relationship between objects, or parts, as a whole. 

While people usually do not pay much mind when things are in proportion, it is usually wildly obvious when things are *not* in proportion. When two objects do not seem to be in proportionate and relative size, it is said to be "out of proportion".


---
# Part 2 - Common 3D Concepts

No matter what you use, Blender, Maya or Microsoft Paint 3D, there are concepts that can be applied universally.


## Polygons
Polygons are n-sided shapes (which basically means they have a number of sides) defined by a group of ordered vertices, as well as edges which are also defined by pairs of vertices.

The components involved in polygons are:
- Vertices (Vertex for singular)
- Edges
- Faces
- UVs

![[Pasted image 20241126204517.png]]


## NURBS (Non-Uniform Rational B-Splines)
These allow us to create completely smooth 3D surfaces and curves. This is useful for constructing 3D organic forms for the smooth and minimal nature that makes up their surfaces.



## Primitive Objects
We have a lot to go over here. Primitive objects are basically the default forms you can make when you press Shift + A in Blender.


### Plane
By default, this is a single quad face with 4 vertices, edges and one face. Basically, its a square piece of paper with no thickness.
<sub>(Side note: A plane has one face, meaning it has one normal, meaning that one 'side' is completely transparent. Keep this in mind if you're using planes in Blender, I suppose.)</sub>

### Cube
Your default cube contains 8 vertices, 12 edges and 6 faces. Of course, this is a 3D object. Most things in Blender happen to be.

Stuff you can make with cubes includes ~~cubes,~~ dice, crates, boxes.

### Sphere (UV Sphere in Blender)
This one is made of quad-faces all around, with a triangle fan at the top and bottom.

### Cylinder
You can make stuff like rods, handles and table legs with these.

### Cone
You can make spikes or hats outta these.

### Torus
The mathematical name for a donut. This is made by rotating a circle around an axis.

### Grid
Your typical quadratic grid that's a subdivided plane. Good for making organic surfaces and landscapes.



## The Pivot Point
This is a point in a form where scale, rotate and mirror transformations are centered. This is good for making the manipulation of a form easier.


## Transformation Tools
This refers to a group of operations you can use to... transform a selected form's properties.

The basic ones are:
- Move
- Rotate
- Scale

Some of these tools do not affect some object. An example of this is scaling the camera in Blender.



## Editing Tools
I suppose we blaze through this... Alright.

### Mirror
Creates a reversed duplicate of the selection.

### Duplicate
Creates an exact duplicate of the selection.

### Smooth
Smooths selected vertices by calculated average angles between the faces.

### Extrude
Extends a certain part of a form or model in a certain direction.

### Inset
Takes selected polygons or faces and subdivides them to create new geometry within the original face.

### Knife (Multi-Cut in Maya)
Cut up geometry by drawing lines in faces.

### Loop Cut (Insert Edge Loop in Maya)
Inserts and slides new edge loops along selected edge.
### Join
Merges all selected objects into the last active object selected.
### Parenting
Group objects such that they function as a singular unit when transforming.



## Topology
This refers to a 3D model's edge distribution and structure. Two similar models can have different topologies.

This affects many aspects of 3D modelling and rendering, such as:
- Ease of editing model's shape
- Ease of applying or editing UVs
- Ease of rigging and animating

Good topology is usually consisting of even-sized faces. Avoid using faces that have 5 or more sides, also known as n-gons.


---
# Part 3 - Materials and Textures

These both are important when making a model, but they are not the same.


## Materials
Materials control the appearance of the form and define the substance the object is made of, the way light interacts with it, its color and its texture.

Shaders are scripts that are attached to the material. These determine the attributes of the material using math n' calculations.

Basically, a material can be made up of textures and/or shaders.


## What Are UVs?
UV Maps are flat representations of a 3D model used to wrap textures. The process of creating a UV map for textures is called **UV Unwrapping**.

A good analogy (according to the slides) is like cutting the sides of a box and laying all of them flat.
![[Pasted image 20241126212542.png]]


If you remember, this is kinda like what Minecraft does with its skins.
![[where-do-i-download-this-skin-v0-43kxzzx8mw1c1.webp]]



## Textures
These are pictures that contain some sort of surface detail for your object. 

Materials have textures in them (as stated previously), but they cannot have more than one texture maps at the same time.

A piece of advice: When unfolding a UV for a model, you can export them as an image and chuck it into photoshop, where you can kinda "paint" your textures, using your exported image as a reference, or even a map.

There are multiple different types of maps when it comes to textures.


- Albedo Map
	- The basis of your material. This defines the base color of an object without any information of highlights or shadows.
- Specular Map
	- This shows the highlights and shininess of a model.
- Normal Map
	- This is a type of bump map that gives a model it's depth and roughness.
- Metalness Map
	- Defines if any part of your material is made of bare metal.

---
Sigh... What a doozy.

\- Mikhail