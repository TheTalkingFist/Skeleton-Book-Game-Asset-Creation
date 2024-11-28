
"Like a Rolling Stone! Like a Rolling Stone! Like the FBI! And the CIA!"
<sup>The Beatles - Dig It</sup>


"If creating concept art is considered an artistic task, then creating and integrating game assets can be considered technical."

As there are constraints in the creation process, the knowledge of the game engine needed to integrate the assets well is technical. Popular **2D game engines** include **GameMaker** and **Construct**. As for both **2D and 3D**, we've got **Unity and Unreal Engine**.

Here, we're learning:

- Camera Angles for 2D Games
- Optimising Assets
- Asset Integration

---

# Camera Angles for 2D Games
Of course, 2D means 2-Dimensional. We only have 2 axes in a 2D space, the X and Y. Yet, 2D games still seem to have tons of depth. How'd they do it? Here, we'll talk about that, and how to make our own assets that look volumetric, even in a flat space.


## Side/Top View
Back in the day, video games were only presented with either the Side or Top view. For example, Donkey Kong and Space Invaders respectively. Of course, some modern games still do this. Dead Cells is still rocking the side view, while Touhou is staying with the top view.

To make things simple, we're gonna talk about Side and Top view in the same vein, because they both belong under the umbrella of Multi-View.

A way we can make objects look 3-Dimensional in a 2-Dimensional space is just by applying the **[[4 - 3D Modelling Techniques#Form|form]] principle when shading**. Basically, imagine it as an actual 3D shape, and then shade it as such. We can see an example of this with the Super Mario Bros. pipes.

![[Pasted image 20241128191148.png]]

See that shading? Makes it look less flat, right? That's because we see it as reflecting light, especially with the highlights and core shadows.



We could also do this with **[[5 - Environment Design#Depth Cues|depth cues]]**. The background, midground and foreground could all be distinguished by using [[5 - Environment Design#Texture|different levels of detail for each layer]]. 

Another thing we could use is **[[5 - Environment Design#Overlap|overlaps]]**. Another another thing we could use is a **parallax** effect.

Remember back in the day, when you went out on long road trips? You'd look out the window and see some trees that are closer and some that are further? And, if you paid enough attention, you'd see that the trees that are closer zoom by you, while the trees further away crawl a bit slower?

That's basically what parallax is. In short, it's making everything in the background plane move slower than everything in the foreground.


Yet another thing we could do is use **dimetric elements** in our scene. Dimetric elements are elements that, while on a flat surface, show more than one side in a distorted proportion. An example of this is this cube.

![[Pasted image 20241128192509.png]]


An example of this *in a game* can be seen in the banger 2016 peak game Castle Crashers.
![[Pasted image 20241128192556.png]]

The characters are in a complete side-view, but the ground is in a sorta kinda top-down-ish view? Basically, it's at an angle. The castle is also at an angle, as we can see a bit of the inner wall.

In real life, this doesn't make sense. Good thing we're talking about games and not real life. Here, it creates a sense of depth in an otherwise flat space.



## Top-Down View
This is a different kinda view. This one is kinda dimetric, and emphasises on the front and top planes or sides of objects.

The main difference between this and a true top view is that with Top-Down, you can see the objects at an angle. This makes it a lot easier to create an illusion of depth and dimensionality.

This view is popular among 2D JRPGs (Pokemon), even to Action-Adventures (Legend of Zelda) and is still used today (Deltarune, OMORI). 



## Isometric
This is one where all axes, X, Y and Z, are presented on screen, and at equal lengths. As such, it is the most 3D presentation in a 2D space. Popular among Real-Time Strategies and 2D Action RPGs.

This one are pretty tough to make assets for. There are tutorials you could look for on youtube, I suppose.
<sub>I'm not gonna link the ones in the powerpoint, I'm sorry.</sub>



# Optimising Assets
We can't just chuck our assets into a game, of course. If we do, a computer could end up in fire and flames. It's best we understand how to conduct some final checks and compile these assets, just to optimise them as best we can.


## Sprites n' Spritesheets

```
sprite
/sprʌɪt/

A single graphic image which can be incorporated into a larger scene.
```
<sup>^^ This is not the actual Google or Oxford definition, this is just taken from the slides to be safe.</sup>

Sprites are a popular way of making large and complex scenes. Reason being that we can easily manipulate each of them separately from everything else in the scene. This gives us greater control over how the scene is rendered, as well as how the player can interact with it.

Most, if not all things in video games are sprites. Player characters, Enemy characters, Projectiles, Walls, Buildings, even UI elements like buttons, icons, graphics.

Once you start making a game, though, you'll soon realise just how many sprites a game can be made of. Just to save you some time and despair, it's hundreds. You can imagine how much processing and memory power this would take.

There's a very simple way to handle this. It's the second (third?) word in the title. Yeah, **Spritesheets**.

Usually, one spritesheet contains a lot of a single character's assets, if not all of them. This includes every frame and animation state of the character at different actions. In the game engine, the animation is played by exposing all frames for a fraction of a second each. 

These spritesheets are a great way of reducing the power a guy's device needs to run the game. Important, especially for games meant to be able to run on mobile, which are statistically crappier.

Of course, there are other ways to optimise your 2D assets. For example, it's always good to scale your images properly. If it's a particle, there's no use exporting it as 1024 x 1024px.


## Modular Environments
Yet another common approach of optimising is to make each asset as a modular piece, meaning that they integrate and combine with other sprites in different situations. They're like legos, I guess.

An extreme case of modular pieces would be tilemaps. Environment tiles, when combined, form the terrain of the world that the player walks on. Excessive use of this, however, creates a blocky looking game. You could avoid this by "rounding off" your terrain with corner caps.

There's another problem when dealing with 3D assets, though. It's good to make sure that each object has a consistent [[4 - 3D Modelling Techniques#The Pivot Point|pivot-point]]. 

By default, all objects have their pivots in the center. This can quickly become problematic, especially when snapping objects to each other. In this scenario, the center of the object would snap, and you'd probably end up with an Amalgamation mess.

It's good to pick a pivot point for every object, like the bottom corner, or front-most, or in any logical location that allows nice, clean snapping.



## Reviewing 3D Assets
Good to check a few things before sending our 3D assets off to the races.
- Polygon Count
	- Keep it to a minimum (of course, without taking away from your art style).
- Normals
	- Ensure that the normals face outwards, else their sides might look invisible.
- Orientation
	- Rotation best happens in the engine, so make sure your orientations are set to 0 for the whole game object.
- N-gons
	- N-gons are faces that have more than 4 vertices and therefore make tessellation difficult.
- Invisible Faces
	- 'Tis a good idea to remove any faces that the player won't see, i.e bottoms of buildings
- Duplicates
	- When using tools like extrude, you could forget to move the geometry, hence leaving a duplicated face. That is not good.


# Asset Integration
This job is usually done by those who created the art assets themselves. They gotta make sure that the assets are imported and can display properly, is proportionate and doesn't result it its own box of bugs.

## File Formats
File formats are not all created equally. Choosing the right one can save a ton of memory.
![[Pasted image 20241128203117.png]]


Same for **3D** file formats.
![[Pasted image 20241128203135.png]]


## Collision Boxes
The hitboxes of your sprites. Unfortunately, technology hasn't advanced far enough that you can import an asset and it will do exactly what you want without any issue.

If you throw in a rock sprite, it's just an image, nothing more. If you want it to do something, for example, prevent the player from walking past it, on it, or into it, you'll need a collision box. This is a bounding box used by the game engine to detect collision between sprites.

This applies to any and all assets, 2D or 3D.

Usually, the game designers set up these boxes. However, the artist must make sure that their artwork does not make the player under/overestimate the size of the sprite or collider. 

![[Pasted image 20241128203538.png]]
On the left, the collider extends too far out, and Mario will appear to walk on air. On the right, the collidor box is too small, and Mario will fall through the tiles.


## Testing
This should be done as early as possible in development, not at the end. We should apply the same to our art assets.

There are a few things we oughta look out for during testing.
- Does the art asset read well?
- Do any of them look out of place?
- Do the animations loop well?
- Do all art assets combine and make [[3 - Intro to UI&UX#CIA for UX|CIA]]?

---
That's it! Good luck for tomorrow (or later today, if you're reading this then)~!

\- Mikhail