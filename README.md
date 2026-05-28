# GDIM 33 In-Class Activities
## W1
### Activity 1
[Inspiration Board](https://docs.google.com/drawings/d/10ok7Fc1FdFxN7G6GRH636GK8RIiuzZ8tItIZ6UjZh34/edit?usp=sharing)

1. Recently I have been making a lot of horror game ideas, so this time I want to do something more relaxed and funny. In my GDIM32 class, I made a lighthearted game, but I did not get to fully implement many of my ideas, so this time I want to try that again. I plan to make a 2D point-and-click puzzle game, because I think it fits visual coding really well. I also want to add a lot of memes, jokes, and other funny elements into the game.
2. I do not think my game idea has that much in common with what my table mates want to make, but they all understood the memes and funny ideas I talked about. They thought those ideas were really funny, and that made me feel more confident about the concept. I also asked them for some background story ideas, and they suggested using a dream setting, which I think is really good, so I added ideas like bedwetting into the game.
3. After talking with our LA, Elijah, I found that he agrees with my idea a lot. We have both played Machinarium, and we both like point-and-click puzzle games. I told him many of my ideas, and he could really imagine the game in the future. He also thinks that making this kind of game with humor and memes is interesting, so I feel more sure about going in this direction.

### Activity 2
[BreakDown](https://docs.google.com/drawings/d/1m1yTcUUbUZ-RVLXbdOLrBOupu3xs25b8Asc6d_fher8/edit?usp=sharing)


## W2


## W3
### Activity 1
Updated BreakDown <img width="1602" height="1111" alt="BreakDown" src="https://github.com/user-attachments/assets/a3f7c8fb-a08c-4844-bdab-63182ef5d25e" />

### Activity 2
1. It is advantageous to save the event name as a Scene variable because if we need to change the event later, it is easier to manage and edit. It can also help reduce bugs, such as spelling mistakes or typos, because we do not need to keep rewriting the event name in multiple places.
2. I think using Debug.Log() during clicking and state changing was very helpful. For example, when I clicked on the NPC, the game did not enter the dialogue state, but the Debug.Log still kept showing “clicked.” That helped me know that the click itself was working, and the problem was in my logic after that. It let me figure out the problem in a more detailed way and helped me see where the bug was coming from.
3. I think Set Cursor Lock State is very relevant to my Vertical Slice because my game needs a lot of dialogue and interaction systems. Most of the time, the cursor will stay visible in the game because the player needs it for clicking and interacting. However, my game is kind of like a trolling game, so maybe hiding the player's cursor in some moments could be funny.
4. I think the concept of game state is very important to my game. My game will need many different states, such as puzzle states, player states, NPC states, and task states. Because of that, state management is very closely connected to my Vertical Slice and is something I need to think about a lot.

## W4
### Activity 1
1. I have one scene in the game. The player plays as a ghost character, and the ghost already has its own animations. The player can move by left-clicking with the mouse. There is also one NPC in the scene. When the player gets close to the NPC, a message will appear that says “Press Space to Talk.” When the player presses the space bar, they will have a dialogue with the NPC and cannot move. Then, after pressing the Continue button, the player can move normally again.
2. My goal for today’s playtesting is to check if my game has any bugs. I also want to test whether the movement feels smooth or uncomfortable to control. Another thing I want to check is whether the character’s collision size is working correctly, and if the player gets stuck on objects or weirdly runs into things.
3. Play Tester: Haoyi Zhang, Pengcheng Qi, Zhengfan Yang, and Allen Gu. They tested my game and gave me some feedback on it. There were no major problems in the game overall. The game worked pretty well for now. I have received one feedback that the buttons in the dialogue system could be improved and made a little better. They also suggested adding character portraits in the dialogue or highlighting the person who is currently talking.


### Activity 2
1. I think a writer can add the text they want very easily. They just need to know where to add the dialogue line and where to add the reply options, and then they can do it without much difficulty. They only need to add the text and the replies they want. Basically, most or all of the writing can be done without changing the code.
2. I think there is almost no limit. The only real limit might be the UI layout for the reply options. If there are too many options on the screen, then you may need to redesign or rearrange the UI. But in terms of dialogue depth and how many layers the conversation can have, I do not think there is really a limit.
3. The “Regenerate Nodes” button refreshes the nodes that we need in Visual Scripting. For example, when we add something new to the code, we may need to regenerate the nodes so Unity can show the new nodes we want to use. In this class activity, I regenerated the nodes at least three times to get the nodes I needed.

#### Extra Credit:
<img width="1920" height="1029" alt="image" src="https://github.com/user-attachments/assets/8a16d29f-11ea-4bc4-a363-1e1e300ee934" />

## W5
### Activity 1

I decided to build a branching dialogue system using ScriptableObjects and Visual Scripting, since I already have my basic dialogue UI and State Machine set up. 

Step 1:
1. Make a DialogueNode C# script (inheriting from ScriptableObject) to hold the npcText and an array for DialogueOptions.
2. Drop a currentNode object variable in the Blackboard so the graph knows exactly where we are in the convo.
3. In the Dialogue State graph, grab the NPC text from the variable and plug it straight into the Canvas UI Set Text node.

(test: Run the game, walk up to the NPC, hit Spacebar, and check if my custom text)

Step 2:
1. Duplicate my UI buttons so there are 4 option buttons on the Canvas, and register their Text components in the Blackboard.
2. In the graph, pull the Options array from the currentNode. Use List: Get Item (Index 0) to grab the first option's reply text, and feed it to the first button.
3. Copy and paste this logic for Index 1, 2, and 3, routing them to the remaining three buttons.

(Test: Run the game and check if all 4 buttons successfully display the custom joke replies)

Step 3:
1. Hook up an On Button Click event node to the first button GameObject.
2. When clicked, extract the Next Node from Index 0 of the Options array, and use a Set Variable node to overwrite the currentNode on the Blackboard.
3. Drag the execution flow All the way back to the start of the UI text sequence to refresh the whole screen.

(Test: Run the game, click the first option button, and test if the screen refreshes to show the next completely different DialogueNode.) 


### Activity 2

For today's class, I made the integrated ScriptableObjects into my Visual Scripting graphs to create a working branching dialogue system. I managed to get the data flowing perfectly: when the player interacts with the cow NPC, the graph correctly reads the ScriptableObject, updates the main NPC text, and extracts an array of choices to populate my 4 UI buttons. So far so good!

## W6
### Activity 1
[Milestone 2 Itch link](https://kaseywan1112.itch.io/gdim33-milestone2)

What's now in my build and play test goal:

In Milestone 1, my game had movement using the NavMesh system. The player can click on the ground with the mouse, and the character will move through the NavMesh. I also had a simple inventory system. When the player gets close to an item, they can press Space to pick it up, and the item will go into the inventory. I also had a simple dialogue system where the player could talk to an NPC, but the dialogue was still very basic. For the new build, I finished a branching dialogue system. Now, when the player talks to an NPC, the dialogue can show the speaker’s portrait and name. I also wrote code so I can choose whether the dialogue is just one line or a branching dialogue with option buttons.

Since I only have a test scene, my playtest goal is to test if the movement, item pickup, and branching dialogue feel clear and smooth.

PlayTest Note: 

During the playtest, players did not really need my hints to understand how to play the game. They could follow the game flow normally, so I think the main gameplay process is working. However, the game still has some bugs and problems that I need to fix.

1. If the player clicks on the character instead of the floor, the character will keep moving toward the camera. I need to make the player character not detectable by the movement raycast.
2. I need to make the camera more top-down. Since my game uses click-to-move on the floor, players need to click the ground easily. Right now, the camera angle makes it a little hard to click the floor, so I should move the camera higher.
3. I need to adjust the interaction buttons. Right now, Space is used for dialogue and interaction, but I think I should separate them more clearly. For example, Space can be used for dialogue, and E or F can be used for item interaction. This will make the controls clearer for players.

### Activity 2
1. Because RGB values are stored between 0.0 and 1.0, when we use Multiply, the final color value will usually become smaller. For example, if we multiply 0.8 by 0.5, the result is 0.4. This is why the color becomes darker and less saturated.
2. If we use Multiply to combine Alpha values, the result will become more translucent. This is because Alpha values are also between 0.0 and 1.0, so multiplying them will usually make the final Alpha value smaller than the original values.
3. The shader gets the UV values from the model’s vertex data. Each vertex has its own UV coordinates, and Unity uses them to determine where the texture should be applied to the model.
4. I think it is interesting because we can use numbers to find the same color more accurately. Different screens or graphics settings may display colors slightly differently, but if we use the same RGB values, we can still find the corresponding color in the shader. This makes color feel more controllable and not just based on what we see with our eyes.


## W7
### Activity 1
1. The data comes from the color data stored in each vertex of the Shiba mesh. The Vertex Color node is basically reading that color information from the mesh.
2. The color is blended because the shader interpolates the color between the vertices on each polygon. So the edge between two colors does not look perfectly sharp.
3. Vertex color is less detailed because the color only exists on the vertices, not every pixel like a texture. So it depends a lot on how many vertices the mesh has. I think vertex color is useful for simple color masks, stylized models, cheap color variation, or debugging.
4. Yes, the back-left leg looks a little wrong. The color looks darker or different there, so that part may have incorrect or inconsistent normals.
5. We could use a debug shader to test UV data. For example, we can show UV values as colors to see if the UVs are stretched, flipped, or not lined up correctly. This would help when a texture looks wrong on the model.
6. The lighting looks wrong because the light direction and the surface normals are facing opposite directions. Because of that, the dot product gives a negative value, so the part that should be bright becomes dark. After we multiply the light direction by -1, the lighting works correctly.
7. We set the Blend Mode to Additive because fire should look bright and glowing. Additive blending makes the bright parts stronger and makes the dark parts almost disappear, so it works better for a fire effect.


## W8
### Activity 1
[milestone3](https://kaseywan1112.itch.io/gdim33-milestone-3)

What's new in my build and play test goal:
Since Milestone 2, my game is no longer just a test scene; it now includes a complete map. I added 2 timeline animations and improved the dialogue system; it now has branching dialogue and character images during conversation. I also made the camera movement smoother. When the camera detects an object blocking the view between the camera and the player, that object will temporarily become hidden. I also changed the character’s NavMesh setup, so the movement feels better than before.

For this playtest goal, my main goal is to see whether players act as I expect. I also want to check if there are any bugs while they are playing. Another goal is to see if players can understand the jokes and memes and get the humor in the game.

PlayTest Note: 

The playtest went smoothly overall, and so far, the game feels good. I still need to make the highlight on the interactable objects make it more obvious and maybe improve the text above the character’s head.

### Activity 2A
1. I think we use the stencil buffer like a mask to decide where the outline can appear. The original Shiba writes a stencil value of 1 first, and then the outline pass checks the stencil value before drawing. Since the outline uses Not Equal, it will not draw on the pixels where the original Shiba already wrote 1. Because of that, the bigger outline version does not cover the real object, and it only shows around the outside of the Shiba.
2. I think the Shiba is the object being drawn almost the same way twice. It is first drawn normally with its original material, and then it is drawn again by the outline render feature with the outline material. The second time, it is basically the same Shiba mesh, but slightly enlarged and colored differently, so it can create the outline around the original object. This is why it is a little inefficient, because Unity has to render the same object more than once for this effect.
3. I think we use ADD instead of MULTIPLY because the different lighting sections are separate parts of the final color. One part is the shadow area, and another part is the lit area. We already use the Step node to split the lighting into different zones, so after that we need to put these zones back together. If we multiply them all together, the final color will become much darker, and the lit area and shadow area will affect each other too much. Using Add is more like combining the shadow part and the light part into one final cel-shaded result.
4. I think changing the Shiba’s layer works because the outline Render Feature is only looking for objects on the Outline layer. When the mouse enters the Shiba, the Visual Scripting Graph changes the Shiba from Default to Outline, so the outline effect turns on. When the mouse exits, it changes the Shiba back to Default, so the outline Render Feature does not draw it anymore. Basically, we are not really turning the shader on and off directly. We are just moving the object in and out of the layer that the outline effect can see.


## W9
### Activity 1
<img width="1098" height="838" alt="WeChat Image_20260528022156" src="https://github.com/user-attachments/assets/a9ac2d34-ba09-4b6a-a245-a805513839fc" />
To make War Thunder's internal structure s X-ray and mouse-over outline effects in Unity, we can split the vehicle model into an opaque internal structure  and a semi-transparent surface skin, rendered later with Transparent queue so that the former naturally shows through the translucent hull. For the highlight outline, we can detect the part with a raycast and draw its inflated mesh in a final pass after all transparent objects, using a queue like Overlay or by injecting it through a CommandBuffer at the AfterRenderingTransparents event to keep the contour sharp on top.

### Activity 2
<img width="1920" height="1029" alt="image" src="https://github.com/user-attachments/assets/a2e6ee77-1726-4a61-bddb-c9a3de68f1f1" />

Today I worked on the outline ShaderGraph for my vertical slice. I added OutlineColor and OutlineThickness, then used the object position and normal vector to push the mesh outward and create an outline shape. But I ran into a bug while setting up the camera/renderer pipeline, so I am still fixing how the effect appears in the Game view. The ShaderGraph is mostly done, but I still need to connect it correctly through the renderer settings.
