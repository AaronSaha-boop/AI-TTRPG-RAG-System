# AI-TTRPG-RAG-System
## A flexible rag system that can take a AI API key, and process it using rules of a multitude of different TTRPG. 

## General Summary

The first iteration of translating a TTRPG into the rag system will be using the rule set of CANE. the way the player interacts is the GUI will set the scene with text and the player will type in a response of 150 charector max to interact with the scene. The story the charector is following is organized by a story arch, that contains chapters, that contain scenes. The general story arc is generated when the player creates a new story, chapters are mile stones within the story arc, each time a a player finishes a chapter the ai will do a deep analysis of the current arc to check if the general story arc still makes sense contexually. You can only have one milestone you are pursuing at a time that follows the story arc and finishes once the "pressure" point builds up to its max and the player either resolves or fails. each scene you take increases the pressure based on your actions, you can never decrease pressure.  

## How is the Data indexed? 

Through the splitting of the documents entered in predictable way, these are context cards that can also link to other context cards.  Catogories tracked by the State is geography and envirament, current setting scene, hunt area. pressure, effects, spells and attacks, player state, monsters, hooks, and npcs. current scene will have a purelt physical description base that will change based on the region and the current weather which is calculated based on the region and the time of year in story plus npcs current mood and player charectors mood if explicetly stated. under the physical description there is what has specific effects when interacted with. each pressure buildup there is a esculation in stakes within the story. the monster have a a goal and hunt pattern that it exuctes on every pressure increases within the hunt area, this will change the physical desctiption of the scene when it becomes the current setting by synthesising the monsters effect with the pysical description and when ignore players and npc mood when building description. player state will have a charector sheet on skills they can do and also a spell/attack sheet. 
## level of ability 
### how many it can effect
  1. one
  2. a few
  3. small group
  4. large group
  5. a crowd
  6. a large crowd
  7. thousand of peopl
  8. many thousand of people
### the size 
  1. human size
  2. heavy furniture 
  3. large animal
  4. vehicle
  5. building
  6. large building
  7. sky scarper
### area of effect 
  1. personal
  2. a few people
  3. entire room
  4. a few rooms
  5. a whole building
  6. a city block
  7. a whole nieghborhood
  8. a whole town
### distance 
  1. touch
  2. same room
  3. across the room
  4. down the block
  5. a few blocks away
  6. across town
  7. visual town
  8. visual range
  9. over the horizon
### speed 
  1. average
  2. fast human
  3. fast animal
  4. cat
  5. train
  6. maglev
  7. airliner
  8. jet fighter


AREA Personal A few people Entire Room A few rooms Whole building A city block A whole
neighborhood A whole town
DISTANCЕ
(0-2 Short)
(3-4 Long) Touch Same Room Across the
Street Down the Block A few blocks
away
Across town Visual range Over the horizon
(5+ Extreme)
SPEED Average human Fast human Fast animal Car Train Maglev Airliner Jet Fighter
MAGNITUDE Small Noticeable Large Very Large Massive Destructive Overwhelming Cataclysmi
