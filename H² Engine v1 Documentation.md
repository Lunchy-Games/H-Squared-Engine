---

# `H² Engine V1 Documentation`

---

`H² Engine V1 Roadmap - ROADMAP` 

`Comprehensive introductory guide for game development - DEVGUIDE`

## `Section Notices` {#section-notices}

| `Section name:` | `Status:` |
| :---- | :---- |
| `Engine Breakdown` | `In editing` |

## 

---

# `H² Engine V1 Intro Dev Guide`

---

# `Document section lookups and information`

---

## `Table of Contents` {#table-of-contents}

`Table of Contents	0`  
[**`Section Notices	0`](#section-notices)**  
[**`Chapter I: Creative Clay	1`](#chapter-i:-creative-clay)**  
[`1. Conceptualize the fundamentals	1`](#conceptualize-the-fundamentals)  
[`2. Let the engine know what entities you will use	1`](#let-the-engine-know-what-entities-you-will-use)  
[`3. Modify your entities’ scripts as needed	1`](#modify-your-entities’-scripts-as-needed)  
[**`Chapter II: Mapping the Magic	2`](#chapter-ii:-mapping-the-magic)**  
[`4. Create costumes for your entities	2`](#create-costumes-for-your-entities)  
[`5. Change the map’s wall colors	2`](#change-the-map’s-wall-colors)  
[`6. Design your map	2`](#design-your-map)  
[**`Chapter III: Saving Success With SEL	3`](#chapter-iii:-saving-success-with-sel)**  
[`7. Open and set up SEL	3`](#open-and-set-up-sel)  
[`8. Create your code strings.	3`](#create-your-code-strings.)  
[`9. Bringing it back over	3`](#9.-bringing-it-back-over)  
[**`Chapter IV: Game Over	4`](#chapter-iv:-game-over)**  
[`10. Make the win condition	4`](#10.-make-the-win-condition)  
[`11. Create the end screen	4`](#11.-create-the-end-screen)  
[**`Chapter V: Wrapping up	5`](#chapter-v:-wrapping-up)**

## 

## 

## `Chapter I: Creative Clay` {#chapter-i:-creative-clay}

`When you start a new project, it can feel overwhelming to have such a blank slate, so let’s start small and use that as the foundation of your project.`

1. ###  `Conceptualize the fundamentals` {#conceptualize-the-fundamentals}

`The first step to creating a game is to conceptualize your game properly, or at the very least, the fundamental aspects:`

- `The gameplay format: puzzle, horror, exploration, etc.`  
- `The stage or game-ending goal: collect all objects, survive for a length of time`  
- `Types of entities you will need.`

`These will all be used in creating your project, helping you make more informed decisions.`

2. ###  `Let the engine know what entities you will use` {#let-the-engine-know-what-entities-you-will-use}

`Once you are done conceptualizing what entities you may use in your game, locate the list named !Name Codex. The engine comes pre-installed with 5 entity types, but you may need to make more. Remember that only completely new types of entities need a different name code. An important note: your entity name cannot contain periods.`

3. ###  `Modify your entities’ scripts as needed` {#modify-your-entities’-scripts-as-needed}

`All entities in the entire game engine are controlled by the Entities sprite. The engine comes with premade scripts for every entity type; however, you may wish to modify them or add more. All entities use custom blocks that link to their personal behavior types, making it easy to isolate and edit individual entity types.`

## `Chapter II: Mapping the Magic` {#chapter-ii:-mapping-the-magic}

`Now that you have completed the scripts and behaviors of your entities, you can begin to design them and the world around them, including how it looks.`

4. ###  `Create costumes for your entities` {#create-costumes-for-your-entities}

`Navigate to the Render sprite. In the costumes tab, you can modify the premade costumes or create new ones for your entities. Note that our system requires costumes to contain “S” followed by the entity name with the same capitalization as in the !Name Codex list.`

5. ###  `Change the map’s wall colors` {#change-the-map’s-wall-colors}

`In the code tab of the Render sprite, navigate to the section with the heading Draw Ray. Here, you can modify the render properties by adjusting the saturation, brightness, and color blocks within.` 

6. ###  `Design your map` {#design-your-map}

	`Enter the Map sprite and create a new costume (or modify the existing one). Make sure to remain at the same scale as the existing map, as our engine does not support vector-mode maps or other scales. We suggest 2px-thick walls and 6px-thick gaps between them.`

## `Chapter III: Saving Success With SEL` {#chapter-iii:-saving-success-with-sel}

`After completing the bulk of your game’s elements, you may be wondering why your entities seem not to be spawning correctly. This is due to how H² processes “new games.” It does this by using our Load system, taking a preset Save-Code string to set up the world. To load your map, player, and entities where you want them, you will need to create a Save-Code that clearly communicates your goals to the engine; however, it isn’t as hard as you may think.`

7. ###  `Open and set up SEL` {#open-and-set-up-sel}

`Open the Scratch project named “SEL Tool” (linked here) and enter the Scratch editor. Run the project. SEL is designed to communicate exactly what our engine does with strings. Before continuing, make sure that the !Name Codex Equivalent list in SEL completely matches the !Name Codex list in the main engine.`

8. ###  `Create your code strings.` {#create-your-code-strings.}

`Look at the list on the left-hand side of the screen, Code Strings. Here, you will note that each given entry has a command.`

1. `An entry featuring a word will correspond directly to setting a map.`  
2. `You place down entities by entering their number in !Name Codex Equivalent, followed by x and y coordinates, and if the “entity” or a “phys” type, direction. (Ex., the “Collect” type is 3rd in the list, so starting a Code String with “3.” means to place a “Collect”). Note that all data points within an entry are separated by periods.`  
3. `The player, being a special entity, follows the same logic as the entity placement; however, the Player is given the ID of “0” (and, like “Entity”s and “Phys”s, requires a direction attribute)`

`As you continue to edit, create, and remove lines from the Code Strings list, you should make sure that What H² Engine Would Do outputs the correct response. If it does not, you may need to double-check your strings.`

### `9. Bringing it back over`  {#9.-bringing-it-back-over}

`When you have finished editing the strings and the What H² Engine Would Do properly matches what you want it to do, select all the output in the Save Code list and copy it. Back in the main engine, locate the SAL sprite. At the top of the code, locate the Load Map From String [string] block for the “Start Scene” event. Delete the string in that block, then paste the string from SEL. Make sure to test it by running the engine and clicking New Game. The Map, Entities, and Player should all have loaded in correctly. If not, check that you copied the full string from SEL, not just a snippet.` 

## `Chapter IV: Game Over` {#chapter-iv:-game-over}

`You’ve successfully completed the hardest part of the development process! Now it’s all just the finishing touches. H² Engine does not have preset end conditions or end screens, but you can use easy checks to trigger the ending or other events!`

### `10. Make the win condition` {#10.-make-the-win-condition}

`Decide a win condition and find out how to trigger it:`

- `If you want the player to win by collecting all collectibles, you can track the premade “collectibles collected” variable, and see when it is the desired amount.`  
- `If you want the player to win by reaching a location, create an invisible hitbox that checks for the player.`

### `11. Create the end screen` {#11.-create-the-end-screen}

`Make a new sprite for the end screen. Make it hidden by default, but upon meeting the win condition, will show and end the game.`

## `Chapter V: Wrapping up` {#chapter-v:-wrapping-up}

`Now that you have completed main development, let’s put in the finishing touches! Open the Main Menu (or any of the other Menu sprites) and edit their costumes as you will. Notice how every button has at least two states (whether or not the mouse pointer is currently hovering over them)`

`And with this, you should be done! Thank you for sharing your story and telling your own tale with the H² Engine developer guide.` 

| Idea | Status |
| :---: | :---: |
| **Additional mobile support** | **Completed** |
| **SEL Tool** | **Completed** |
| **3rd Person camera mode** | **Consideration postponed** |
| **Development Guide** | **Completed** |
| **Hitbox event triggers. (inverse hitbox idea, where a list will show if each clone is touching )** | **Under Consideration** |
| **Verification Update: Remove/shorten audio delay check Add check to verify all sprite types have a costume** | **Under Consideration** |
| **Completely “blank” copy of H² Engine for developers to use.** | **Approved, will be worked on** |
| **Developer Toolkit Sprite Moves to the mouse pointer when space is pressed (gives coordinates to use in SEL)** | **Under Consideration** |
| **YouTube video to promote H² Engine** | **Consideration postponed** |

`The H² Engine is structured based on the order of development. The majority of the game engine - including all menus, controller and mobile compatibility, dynamic entity logic, and saving and loading - were created around the DIST-L Engine (the main 3D rendering engine). Please remember this as we break down the engine.`

## `Verification`

`When you first run the engine, you will be presented with the verification screen. The verification is triggered by a variable that records the user’s username (named EUI). If the variable doesn’t match the user’s username, it will trigger verification. When you load the project (or reload the tab), it resets variables to their defaults, so it will trigger each time you load the project.`

`During verification, two checks are performed:`

- `During the first check, two audio clips are played. These audio clips are silent for the viewer and are both timed. If the exact ratio between them is within the set range, it indicates they are unmodified and that there are no unexpected lag spikes.`  
- `The second check, performed simultaneously, triggers a count of all sprites. This ensures that no sprites are missing or unaccounted for.`

	`After passing verification, it sets the EUI variable to match the user’s EUI, preventing verification from triggering again until the project is reloaded. However, if you are developing a game in the engine, after you complete verification (by saving the project), the EUI variable's default is set to your username, preventing verification.`

## 	`The menus`

`All menus in this game operate very similarly on the surface; however, each has a completely different structure to suit its needs. For example, in the main menu, all buttons close the main menu to open other menus, enter the main engine, or trigger load sequences. In contrast, the settings menu uses multi-layered checks to match the buttons to settings toggles, and only one closes the menu. Additionally, the credits and updates menus use the same script, with only one button that always returns to the main menu.`

## `Ent2Screen`

`The Ent2Screen sprite takes the positions of all entities in the map and calculates where they would appear on screen, simultaneously picking whether an entity should be culled, alongside the distance cutoffs for the entity-paning system used in the render.`